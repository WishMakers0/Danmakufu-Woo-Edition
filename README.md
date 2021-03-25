# Touhou Danmakufu ph3.5 ~ Woo Edition
All hail our lord and savior Mima and our queen, Kogasa's Woo. This version of Danmakufu is made for the purposes of both optimization and fixing some issues with the original source that mkm dropped. (See James7132's repo for a link to the original download) <b>This version of Danmakufu is completely backwards compatible with ph3. If something doesn't work as expected, please let me know.</b> My Discord tag is WishMakers#0385 if you need to reach me.

## Changes in Master Branch
Here's a list of changes compared to original Danmakufu that may enable your computer to use it better.
 * Changes the way RNG is determined to be much more stable than previously (mt19937 compared to a Mersenne Twister from 1996, lmao)
 * Removes a lot of repeated function calls (in bullet movement only as of 6/24/2019)
 * Removes a LOT of unnecessary vertices calculated (but not used) when drawing curvy lasers (see Special Thanks)
 * Enables a lot of optimization flags that mkm for some reason disabled (basically everything under /O2)
 * Attempts to fix the window resolution issue (not quite 640x480) that occurs with the source when built, but not the original ph3 build.
 * Dat extraction now works properly, enables the use of games like Kaisendo's Hollow Song of Birds and other games that use dat archives.
 * Side bars in fullscreen are now black as opposed to the ubiquitous DNH Gray.

## Requirements
 * zlib
</br>Best and recommended way to obtain it is to use [vcpkg](https://github.com/Microsoft/vcpkg) C++ Library Manager.

## Known Issues
 * Wine 4.12.1 (confirmed on macOS at least) suffers some scaling problems with the window size, being 9 pixels too wide and 7 pixels too tall.  This causes some nasty scaling on in-game assets, possibly a result of old Windows size calls not being 100% compatible with Wine releases.

## Special Thanks
Natashi - for the code that made curvy lasers run a lot better than what I could do
</br>Trickysticks - for the woo art that graced the world
</br>UltimaOmega - for helping me with my sorry excuse for zlib code

## Contributions
Unlike the original source, this version is *technically* in active development (though my primary focus will be Danmakufu Remastered - check out Ultima's repo for that here) so pull requests are absolutely accepted provided they don't break the game. Though bear in mind that as this version of DNH still relies on mkm's original source code (most of which is either very unoptimized even with optimization flags or is very outdated in execution), there is only so far we can go in attempting to make it better.
</br>In addition, *this build will be focused on optimization and performance improvements only.* If you want to suggest brand new features, bug fixes, etc. please turn your attention to Danmakufu Remastered instead - this version is made to be completely backwards compatible, and as such new features can't simply be added.

## New Features Branch
The "newfeatures" branch and its releases exists for those who wish to have some minor functionality improvements that aren't completely 1:1 with original PH3, but would rather not wait until DNH:R is released to use them.  These changes may be mirrored in DNH:R's PH3 compatibility, but as of 8/9/2019 they are currently unimplemented.

## License
zlib library has its own license, please check zlib.h in the repo for that information.</br></br>
(quoted from James7132's repo of the original source, maintaining the same license.) </br>This code is licensed under the NYSL (Niru nari Yaku nari Suki ni shiro License'). Main translated points:

 * "No warranty" disclaimer is explicitly included.
 * Modified version of the software MUST be distributed under the responsibility of the distributer.
 * Official version is written in Japanese.
