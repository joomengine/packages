### JCB! Site View
# Looking (looking)

Looking at a look

## HTML:
```html
<article class="uk-comment uk-comment-primary">
    <header class="uk-comment-header uk-grid-medium uk-flex-middle" uk-grid>
        <div class="uk-width-auto">
            <img class="uk-comment-avatar" src="https://via.placeholder.com/80" width="80" height="80" alt="">
        </div>
        <div class="uk-width-expand">
            <h4 class="uk-comment-title uk-margin-remove"><strong><?php echo $this->escape($this->item->name); ?></strong></h4>
            <ul class="uk-comment-meta uk-subnav uk-subnav-divider uk-margin-remove-top">
                <li><?php echo Text::_('Hits'); ?>: <?php echo $this->item->hits; ?></li>
            </ul>
        </div>
    </header>
    <div class="uk-comment-body">
        <p><?php echo $this->item->description; ?></p>

        <?php if (!empty($this->item->files)): ?>
            <div class="uk-margin">
                <?php echo Joomla___7ab82272_0b3d_4bb1_af35_e63a096cfe0b___Power::render('demolookfiledisplay', ['data' => $this->item->files, 'target' => 'look', 'entity' => $this->item->guid, 'remove_delete' => true]); ?>
            </div>
        <?php endif; ?>

        <?php if (!empty($this->item->guidEntityDetailD)): ?>
            <div class="uk-margin">
                <button class="uk-button uk-button-default uk-button-small" uk-toggle="target: #more-details-090">
                    <?php echo Text::_('More Details'); ?>
                </button>
            </div>
        <?php endif; ?>
    </div>
</article>

<?php if (!empty($this->item->guidEntityDetailD)): ?>
    <!-- This is the modal -->
    <div id="more-details-090" uk-modal>
        <div class="uk-modal-dialog uk-modal-body">
            <button class="uk-modal-close-default" type="button" uk-close></button>
            <h2 class="uk-modal-title"><?php echo Text::_('More Information'); ?></h2>
            <div class="uk-grid-small uk-child-width-expand@s uk-text-center" uk-grid>
                <?php foreach ($this->item->guidEntityDetailD as $more): ?>
                    <div class="uk-card uk-card-default uk-card-hover uk-card-body uk-width-1-2@m uk-margin-small-bottom">
                        <dl class="uk-description-list uk-description-list-divider">
                            <?php if (Super___1f28cb53_60d9_4db1_b517_3c7dc6b429ef___Power::check($more->dateofbirth)): ?>
                                <dt><?php echo Text::_('Birth day'); ?></dt>
                                <dd><?php echo Joomla___cf3b95c1_ba56_4193_8eb4_9164582b7f55___Power::fancyDate($this->escape($more->dateofbirth)); ?></dd>
                            <?php endif; ?>
                            <?php if (Super___1f28cb53_60d9_4db1_b517_3c7dc6b429ef___Power::check($more->email)): ?>
                                <dt><?php echo Text::_('Email'); ?></dt>
                                <dd><?php echo $this->escape($more->email); ?></dd>
                            <?php endif; ?>
                            <?php if (Super___1f28cb53_60d9_4db1_b517_3c7dc6b429ef___Power::check($more->mobile_phone)): ?>
                                <dt><?php echo Text::_('Mobile'); ?></dt>
                                <dd><?php echo $this->escape($more->mobile_phone); ?></dd>
                            <?php endif; ?>
                            <?php if (Super___1f28cb53_60d9_4db1_b517_3c7dc6b429ef___Power::check($more->website)): ?>
                                <dt><?php echo Text::_('Website'); ?></dt>
                                <dd><?php echo $this->escape($more->website); ?></dd>
                            <?php endif; ?>
                        </dl>
                    </div>
                <?php endforeach; ?>
            </div>
        </div>
    </div>
<?php endif; ?>
```

> Deliver dynamic, custom front-end experiences with this reusable Site View crafted for seamless data flow and design flexibility in JCB.

### Used in [Joomla Component Builder](https://www.joomlacomponentbuilder.com) - [Source](https://git.vdm.dev/joomla/Component-Builder) - [Mirror](https://github.com/vdm-io/Joomla-Component-Builder) - [Download](https://git.vdm.dev/joomla/pkg-component-builder/releases)

---
[![Joomla Volunteer Portal](https://img.shields.io/badge/-Joomla-gold?logo=joomla)](https://volunteers.joomla.org/joomlers/1396-llewellyn-van-der-merwe "Join Llewellyn on the Joomla Volunteer Portal: Shaping the Future Together!") [![Octoleo](https://img.shields.io/badge/-Octoleo-black?logo=linux)](https://git.vdm.dev/octoleo "--quiet") [![Llewellyn](https://img.shields.io/badge/-Llewellyn-ffffff?logo=gitea)](https://git.vdm.dev/Llewellyn "Collaborate and Innovate with Llewellyn on Git: Building a Better Code Future!") [![Telegram](https://img.shields.io/badge/-Telegram-blue?logo=telegram)](https://t.me/Joomla_component_builder "Join Llewellyn and the Community on Telegram: Building Joomla Components Together!") [![Mastodon](https://img.shields.io/badge/-Mastodon-9e9eec?logo=mastodon)](https://joomla.social/@llewellyn "Connect and Engage with Llewellyn on Joomla Social: Empowering Communities, One Post at a Time!") [![X (Twitter)](https://img.shields.io/badge/-X-black?logo=x)](https://x.com/llewellynvdm "Join the Conversation with Llewellyn on X: Where Ideas Take Flight!") [![GitHub](https://img.shields.io/badge/-GitHub-181717?logo=github)](https://github.com/Llewellynvdm "Build, Innovate, and Thrive with Llewellyn on GitHub: Turning Ideas into Impact!") [![YouTube](https://img.shields.io/badge/-YouTube-ff0000?logo=youtube)](https://www.youtube.com/@OctoYou "Explore, Learn, and Create with Llewellyn on YouTube: Your Gateway to Inspiration!") [![n8n](https://img.shields.io/badge/-n8n-black?logo=n8n)](https://n8n.io/creators/octoleo "Effortless Automation and Impactful Workflows with Llewellyn on n8n!") [![Docker Hub](https://img.shields.io/badge/-Docker-grey?logo=docker)](https://hub.docker.com/u/llewellyn "Llewellyn on Docker: Containerize Your Creativity!") [![Open Collective](https://img.shields.io/badge/-Donate-green?logo=opencollective)](https://opencollective.com/joomla-component-builder "Donate towards JCB: Help Llewellyn financially so he can continue developing this great tool!") [![GPG Key](https://img.shields.io/badge/-GPG-blue?logo=gnupg)](https://git.vdm.dev/Llewellyn/gpg "Unlock Trust and Security with Llewellyn's GPG Key: Your Gateway to Verified Connections!")