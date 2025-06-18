### JCB! Layout
# Importer Easy Mapping

## Key:
```php
echo LayoutHelper::render('importereasymapping', [?]);
```

## HTML:
```html
<div class="uk-container uk-margin-large-top">
	<h1 class="uk-heading-divider"><?php echo Text::_('Data importer documentation'); ?></h1>

	<p><?php echo Text::_('Welcome to the data importer! This tool allows you to upload spreadsheets, map columns to database fields, and track the status of imports in a queue. Below is a step-by-step guide on how to use this feature effectively.'); ?></p>

	<h2 class="uk-heading-bullet"><?php echo Text::_('Understanding the importer interface'); ?></h2>

	<p><?php echo Text::_('The import interface consists of two main tabs:'); ?></p>

	<ul class="uk-list uk-list-bullet">
		<li><strong><?php echo Text::_('Importer tab'); ?>:</strong> <?php echo Text::_('This is where you upload your spreadsheet, map the columns to the database, and start the import process.'); ?></li>
		<li><strong><?php echo Text::_('Queue tab'); ?>:</strong> <?php echo Text::_('This displays the status of your imports, showing whether they are pending, processing, completed, or have errors.'); ?></li>
	</ul>

	<h2 class="uk-heading-bullet"><?php echo Text::_('Steps to import data'); ?></h2>

	<ol class="uk-list uk-list-decimal">
		<li>
			<strong><?php echo Text::_('Upload a spreadsheet'); ?></strong>
			<ul class="uk-list uk-list-circle">
				<li><?php echo Text::_('Drag and drop your spreadsheet into the designated upload area (outlined with dotted lines) or click to select a file.'); ?></li>
				<li><?php echo Text::_('The system supports standard spreadsheet formats such as .xlsx and .csv.'); ?></li>
			</ul>
		</li>
		<li>
			<strong><?php echo Text::_('Map columns'); ?></strong>
			<ul class="uk-list uk-list-circle">
				<li><?php echo Text::_('After uploading, you will be prompted to map the spreadsheet columns to the corresponding database fields.'); ?></li>
				<li><?php echo Text::_('If you used the correct header names (as provided in the example file), the system will automatically map the columns for you.'); ?></li>
				<li><?php echo Text::_('You can adjust any mappings before proceeding.'); ?></li>
			</ul>
		</li>
		<li>
			<strong><?php echo Text::_('Start the import'); ?></strong>
			<ul class="uk-list uk-list-circle">
				<li><?php echo Text::_('Once the mappings are confirmed, submit the import.'); ?></li>
				<li><?php echo Text::_('The system will queue the import process.'); ?></li>
			</ul>
		</li>
		<li>
			<strong><?php echo Text::_('Monitor the import status'); ?></strong>
			<ul class="uk-list uk-list-circle">
				<li><?php echo Text::_('Navigate to the queue tab to track the progress of your import.'); ?></li>
				<li><?php echo Text::_('Imports can have the following statuses:'); ?>
					<ul class="uk-list uk-list-bullet">
						<li><strong><?php echo Text::_('Pending'); ?>:</strong> <?php echo Text::_('Waiting to be processed.'); ?></li>
						<li><strong><?php echo Text::_('Processing'); ?>:</strong> <?php echo Text::_('Currently being imported.'); ?></li>
						<li><strong><?php echo Text::_('Completed'); ?>:</strong> <?php echo Text::_('Successfully imported.'); ?></li>
						<li><strong><?php echo Text::_('Error'); ?>:</strong> <?php echo Text::_('Issues encountered (with error messages displayed).'); ?></li>
					</ul>
				</li>
			</ul>
		</li>
	</ol>

	<h2 class="uk-heading-bullet"><?php echo Text::_('Using the example file'); ?></h2>

	<div class="uk-alert-primary" uk-alert>
		<p><strong><?php echo Text::_('Why use the example file?'); ?></strong></p>
		<ul class="uk-list uk-list-bullet">
			<li><?php echo Text::_('It includes the correct header names for database fields.'); ?></li>
			<li><?php echo Text::_('If you use these headers in your import file, the system will automatically map columns, reducing manual effort.'); ?></li>
			<li><?php echo Text::_('Particularly helpful for large datasets with many columns.'); ?></li>
		</ul>
	</div>

	<p><?php echo Text::_('To download the example file, click the "Example" button at the top of the importer tab.'); ?></p>

	<h2 class="uk-heading-bullet"><?php echo Text::_('What to expect after importing'); ?></h2>

	<p><?php echo Text::_('Once the import is submitted, the system processes it in the background. Here’s what happens next:'); ?></p>

	<ul class="uk-list uk-list-bullet">
		<li><?php echo Text::_('The import appears in the queue tab with its status.'); ?></li>
		<li><?php echo Text::_('If errors occur, messages will be displayed under the import entry in the queue.'); ?></li>
		<li><?php echo Text::_('Successful imports will be marked as completed.'); ?></li>
		<li><?php echo Text::_('You can review errors and re-upload a corrected file if needed.'); ?></li>
	</ul>

	<h2 class="uk-heading-bullet"><?php echo Text::_('Common issues and troubleshooting'); ?></h2>

	<ul class="uk-list uk-list-bullet">
		<li><strong><?php echo Text::_('Columns are not mapping correctly'); ?>:</strong> <?php echo Text::_('Ensure your spreadsheet headers match those in the example file.'); ?></li>
		<li><strong><?php echo Text::_('File upload fails'); ?>:</strong> <?php echo Text::_('Check if your file is in a supported format (.xlsx, .csv).'); ?></li>
		<li><strong><?php echo Text::_('Import remains stuck in "Pending"'); ?>:</strong> <?php echo Text::_('There may be a high queue volume; try again later.'); ?></li>
	</ul>

	<div class="uk-alert-danger" uk-alert>
		<p><strong><?php echo Text::_('Note'); ?>:</strong> <?php echo Text::_('Large files may take longer to process. You can check the queue for status updates.'); ?></p>
	</div>

	<h2 class="uk-heading-bullet"><?php echo Text::_('Conclusion'); ?></h2>

	<p><?php echo Text::_('The data importer provides a streamlined way to upload and process spreadsheets while ensuring accuracy with column mapping. By following the steps above, you can efficiently import your data and monitor its progress.'); ?></p>
</div>
```

> Enhance your Joomla components with a reusable layout that ensures consistent design, easy updates, and full compatibility within the JCB framework.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")