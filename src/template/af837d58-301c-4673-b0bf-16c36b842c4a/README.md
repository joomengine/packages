### JCB! Template
# Importer Area

## Key:
```php
$this->loadTemplate('importerarea', [?]);
```

## PHP:
```php
if (!empty($this->item->file_type))
{
$target = base64_encode('[[[sview]]]');
[CUSTOMCODE=vdmUploaderConfig+vdm-uikit-uploader,file_vdm_uploader,getFileTypeDetails,uploadFile,displayImportColumns,deleteFile]
[CUSTOMCODE=addUikitThreeToAdminViews]
}
```

## HTML:
```html
<?php if (empty($this->item->file_type)): ?>
<div class="alert alert-warning" role="alert">
	<?php echo Text::_('The import file type has not been configured. Please contact your system administrator for assistance.'); ?>
</div>
<?php else: ?>
<select id="file_type" name="file_type" style="display: none;">
	<option value="<?php echo $this->item->file_type; ?>" selected><?php echo Text::_('Import Type'); ?></option>
</select>
<div id='file_vdm_uploader' class='vdm-uikit-uploader uk-placeholder uk-text-center'
	data-type-id='file_type'
	data-progressbar-id='file_vdm_progressbar'
	data-display-id='file_vdm_display'
	data-success-id='file_vdm_success'
	data-error-id='file_vdm_error'
	data-allowed-format-id='file_vdm_allowed_format'
	data-file-type-id='file_vdm_file_type'
>
    <span uk-icon='icon: cloud-upload'></span>
    <span class='uk-text-middle'><?php echo Text::_('Attach'); ?> <span id='file_vdm_file_type'>file</span> <?php echo Text::_('by dropping them here or'); ?></span>
    <div uk-form-custom>
	   <input type='file'>
	   <span class='uk-link'><?php echo Text::_('selecting one'); ?></span> <span id='file_vdm_allowed_format'></span>
    </div>
</div>
<progress id='file_vdm_progressbar' class='uk-progress' value='0' max='100' hidden></progress>
<br>
<div id='file_vdm_success' hidden></div>
<div id='file_vdm_error' hidden></div>
<div id='file_vdm_display' hidden></div>
<script type="text/javascript">
document.addEventListener('vdm.uikit.display.beforeFilesDisplay', function(event) {
    let state = event.detail?.result?.state ?? 0;
    if (state === 1 && window.VDM?.uikit?.config?.target_class) {
        let targetClass = window.VDM.uikit.config.target_class;
        let elements = document.getElementsByClassName(targetClass);

        for (let i = 0; i < elements.length; i++) {
            elements[i].style.display = 'none';
        }
    }
});
document.addEventListener('vdm.uikit.uploader.complete', function(event) {
    let response = event.detail?.xhr?.responseText ?? null;
    if (response) {
        try {
            // Parse the response JSON
            response = JSON.parse(response);
            // Check for the 'error' property in the response
            if (response.error) {
                // Show a Uikit notification for the error
                window.UIkit.notification({
                    message: response.error,  // Display the error message
                    status: 'danger',          // Set the notification type to 'error'
                    pos: 'top-center',         // Position of the notification
                    timeout: 7000              // Display time in milliseconds
                });
            }
        } catch (e) {
            console.error('Error parsing JSON response:', e);
        }
    }
});
document.addEventListener('vdm.uikit.delete.beforeFileRemoveFromUI', function(event) {
    if (window.VDM?.uikit?.config?.target_class) {
        let targetClass = window.VDM.uikit.config.target_class;
        let elements = document.getElementsByClassName(targetClass);
        for (let i = 0; i < elements.length; i++) {
            elements[i].style.display = '';
        }
        let subformArea = document.getElementById('subform-display-area');
        if (subformArea) {
            subformArea.style.display = 'none';
        }
    }
});
</script>
<?php endif; ?>
```

> Structure your Joomla views with a reusable template that ensures consistent rendering, streamlined development, and easy customization within JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")