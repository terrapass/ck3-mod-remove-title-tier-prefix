<a href="https://steamcommunity.com/sharedfiles/filedetails/?id=2601437909"><img src="https://img.shields.io/endpoint.svg?url=https%3A%2F%2Fshieldsio-steam-workshop.jross.me%2F2601437909&style=for-the-badge" alt="Steam Workshop subscribers"></a>

Remove Title Tier Prefix (Toggle Short Name)
============================================
_(a Crusader Kings III mod)_

<img src="https://raw.githubusercontent.com/terrapass/ck3-mod-remove-title-tier-prefix/master/thumbnail.png" alt="Mod Thumbnail" width="250" height="250" />

This small mod allows you to remove or restore tier prefix (e.g. "Empire of") for any title you hold. This means you can get more creative with naming your titles without running into "Kingdom of Some Kingdom" and other such repetitions.

Ever wanted to rename Papacy title for your custom faith to something cool, like say "Church of Pancakes",  but discovered that when you did it turned into "Duchy of Church of Pancakes"? Well, this mod has you covered, since you can now disable this annoying tier prefix for your title with the click of a button and later re-enable it just as easily, should you change your mind.

If you've played CK2, you might remember this option as "Toggle Short Name" checkbox in title rename window.
As it turns out, It's also coming to CK3 later this year in patch 1.5 as part of the [new Coat of Arms designer](https://forumcontent.paradoxplaza.com/public/739696/1_main_screen.PNG).
In the meantime, this mod provides a solution for the current version of the game.

**Compatible** with existing saves and can be removed without breaking saves (though note that changes made to tier prefix visibility will remain in your save even after mod removal).
Should be compatible with any mod that does not modify title UI.

**Now compatible** with [Title Manager](https://steamcommunity.com/sharedfiles/filedetails/?id=2436624088) mod by Xman7373.

Currently **incompatible** with Randomized CoA mod.

Under the hood
--------------

The game already has support for controlling visibility of title tier prefixes, via `definite_form = yes` in title configuration, and it's used internally for titles such as the Papacy (see `k_papal_state` in the game's `00_landed_titles.txt`), the HRE and the Byzantine Empire, though until now there was no way for players to change this setting themselves, short of manually modifying a savegame or using debug mode explorer. There is also a title scope effect called `set_definitive_form`, allowing a dynamic application of this property to an existing title.

Essentially, all this mod does is [invokes](https://github.com/terrapass/ck3-mod-remove-title-tier-prefix/blob/master/common/scripted_guis/remove_title_prefix.txt) the aforementioned `set_definitive_form` effect for the currently selected title at the click of [a new UI button](https://github.com/terrapass/ck3-mod-remove-title-tier-prefix/blob/master/gui/window_title.gui#L142).
