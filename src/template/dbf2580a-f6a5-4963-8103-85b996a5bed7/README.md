### JCB! Template
# Importer Queue

## Key:
```php
$this->loadTemplate('importerqueue', [?]);
```

## PHP:
```php
function reorderObjectKeysByMap(&$arrayOfObjects, $headers)
{
	$headerKeys = array_keys($headers); // Get the desired key order from the headers
	foreach ($arrayOfObjects as &$object)
	{
		$array = (array) $object; // Convert object to associative array
		// Create a new array with keys ordered according to the headers
		$reorderedArray = [];
		foreach ($headerKeys as $key)
		{
			// Add the key in the defined order, even if it doesn't exist in the object
			$reorderedArray[$key] = isset($array[$key]) ? $array[$key] : null;
		}
		// Convert the reordered array back to an object
		$object = (object) $reorderedArray;
	}
}

if ($this->queue)
{
	$table_id = Super___1f28cb53_60d9_4db1_b517_3c7dc6b429ef___Power::random(7);
	$headers = [
		'guid' => '',
		'target' => '',
		'number' => '',
		'file_name' => Text::_('File Name'),
		'import_status' => Text::_('Status'),
		'created' => Text::_('Date')
	];
	// Reorder the keys of each object according to the map
	reorderObjectKeysByMap($this->queue, $headers);
}

// Create the message endpoint
$url = '';
if ($this->app->isClient('site'))
{
	$url = Joomla___eecc143e_b5cf_4c33_ba4d_97da1df61422___Power::root();
}
$token = Joomla___5ba38513_5c4f_4b0d_935e_49e986a6bce8___Power::getFormToken();
$messageEndpoint = "{$url}index.php?option=com_[[[component]]]&task=ajax.getMessages&format=json&raw=true&{$token}=1";

// create the modal details for messages
$message_id = 'message-modal-' . Super___1f28cb53_60d9_4db1_b517_3c7dc6b429ef___Power::random(7);
$message_header = Text::_('Import Message Log(s)');
$message_content = '<div id="' . $message_id . '-area">...</div>';
```

## HTML:
```html
<h3><?php echo Text::_('Import Queue'); ?></h3>
<?php if ($this->queue): ?>

<?php echo Joomla___7ab82272_0b3d_4bb1_af35_e63a096cfe0b___Power::render('table',
	[
		'id' => $table_id,
		'items' => $this->queue,
		'headers' => $headers,
		'init' => false
	]
); ?>

<?php echo Joomla___7ab82272_0b3d_4bb1_af35_e63a096cfe0b___Power::render('modal',
	[
		'id' => $message_id,
		'header' => $message_header,
		'content' => $message_content,
		'modal_class' => 'uk-flex-top',
		'dialog_class' => 'uk-modal-dialog uk-modal-body uk-margin-auto-vertical'
	]
); ?>

<script type="text/javascript">
// message endpoint to fetch the messages
const messageEndpoint = '<?php echo $messageEndpoint; ?>';
// Get the element with ID 'message-modal-xxx' to manage the modal
const modalElement = document.getElementById('<?php echo $message_id; ?>');
// init our table
document.addEventListener("DOMContentLoaded", function() {
	var <?php echo $table_id; ?> = new DataTable('#<?php echo $table_id; ?>', {
		order: [[ 2, "desc" ]],
		info: true,
		paging: true,
		deferRender: true,
		select:  true,
		columnDefs: [
			{ 'targets': [ 0, 1 ], 'visible': false, 'searchable': false }
		],
		columns: [
			{
				data: 'guid'
			},
			{
				data: 'target'
			},
			{
				data: 'number'
			},
			{
				data: 'file_name'
			},
			{
				data: 'import_status',
				render: function(data, type, row) {
					if (type === 'display' && data.length > 0) {
						return data + '  <a href="#" onclick="getMessages(\"row.guid\", \"row.target\");" class="uk-icon-button" uk-icon="info"></a>';
					}
					return data;
				}
			},
			{
				data: 'created'
			}
		]
	});
	// Adjust the table size when the tab is shown using the custom event
	document.addEventListener('joomla.tab.show', function() {
		const tableContainer = document.querySelector('#<?php echo $table_id; ?>');
		tableContainer.style.width = '100%'; // Ensure the container is 100% width
		<?php echo $table_id; ?>.columns.adjust().draw();
	});
	<?php echo $table_id; ?>.on( 'select', function ( e, dt, type, indexes ) {
		if ( type === 'row' ) {
			// get the data from the row
			let data = <?php echo $table_id; ?>.rows( indexes ).data();
			// get the guid
			let guid = data[0].guid;
			// get the target
			let target = data[0].target;
			// get the message for this import item
			getMessages(guid, target);
		}
	});
});

/**
 * Retrieves messages from the server and handles the response.
 * 
 * @param {string} entity - The GUID of the item to retrieve messages for.
 * @param {string} target - The target parameter for the request.
 */
function getMessages(entity, target) {
    // Ensure the messageEndpoint variable is defined
    if (typeof messageEndpoint === 'undefined') {
        console.error('Error: messageEndpoint is not defined.');
        return;
    }

    // Build the URL with encoded query parameters to prevent injection attacks
    const url = `${messageEndpoint}&entity=${encodeURIComponent(entity)}&target=${encodeURIComponent(target)}`;

    // Make a GET request using the Fetch API
    fetch(url)
        .then(response => {
            // Check if the response status is OK (status code 200-299)
            if (!response.ok) {
                throw new Error(`Network response was not ok (Status: ${response.status})`);
            }
            // Parse the response body as JSON
            return response.json();
        })
        .then(data => {
            // Check if the response contains an 'error' property
            if (data.error) {
                // Display the error message using UIkit.notification with 'danger' status
                UIkit.notification({
                    message: data.error,
                    status: 'danger',
                    pos: 'top-right',
                    timeout: 5000
                });
                return; // Stop further processing
            }

            // Check if the response contains an 'html' property
            if (data.html) {
                // Get the element with ID 'message-modal-xxx-area' to insert HTML content
                const modalContentElement = document.getElementById('<?php echo $message_id; ?>-area');
                if (modalContentElement && modalElement) {
                    // Insert the HTML content into the modal area
                    modalContentElement.innerHTML = data.html;
                } else {
                    console.error('Error: Element with ID "message-modal" not found.');
                    return;
                }

                // Display the modal using UIkit.modal
                UIkit.modal(modalElement).show();
            }
        })
        .catch(error => {
            // Handle any errors that occurred during the fetch operation
            console.error('Fetch error:', error);
            UIkit.notification({
                message: 'An error occurred while fetching messages.',
                status: 'danger',
                pos: 'top-right',
                timeout: 5000
            });
        });
}
</script>
<?php else: ?>
	<div class="alert alert-success" role="alert">
		<p><?php echo Text::_('All your imports will be listed here, with their status, and any other related details.'); ?></p>
	</div>
<?php endif; ?>
```

> Structure your Joomla views with a reusable template that ensures consistent rendering, streamlined development, and easy customization within JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")