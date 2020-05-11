# Touhou Danmakufu ph3.5 ~ Woo Edition
All hail our lord and savior Mima and our queen, Kogasa's Woo. This version of Danmakufu is made for the purposes of both optimization and fixing some issues with the original source that mkm dropped. (See James7132's repo for a link to the original download) <b>The master branch version of this repo is completely backwards compatible with ph3. This branch will contain functions that are not in original PH3.  If something doesn't work as expected, please let me know.</b> My Discord tag is WishMakers#0426 if you need to reach me.

<b>As of 5/11/2020, Woo will not be updated any more.  I'm passing the torch to Natashi and ph3sx for Danmakufu scripting improvements. https://github.com/Natashi/Touhou-Danmakufu-ph3sx</b>

## Changes To New Feature Branch
If you would like detailed information on each function, please check out a full explanation inside the corresponding version's changelog.
Credits for each function can be found inside the changelogs as well.

###### [ph3.5 .1 pre6a open nf3]
 * Alpha values in Render Targets will now render properly
 * Added SetShotGrazeInvalidFrame(frames)
	- Sets the default amount of frames that must pass before a bullet can be grazed again for all bullets
 * Added SetShotInvalidIntersectionDistance(distance)
	- Sets the distance in pixels to automatically disable and enable non-laser bullet hitboxes
	- IMPORTANT: Check the version changelog for more details on this function.
 * Added ObjShot_SetGrazeInvalidFrame(ObjShotID, frames)
	- Sets the amount of frames that must pass before the specified bullet can be grazed again
 * Added ObjShot_GetGrazeStatus(ObjShotID)
	- Returns true if the player is colliding with the specified bullet's graze hitbox
 * ObjShot_SetDamageReductionRate(ObjShotID, Reduction Rate)
	- Sets the rate at which the specified bullet's damage will be reduced by based on the total number of bullets colliding with a single enemy on a single frame.
 * ObjShot_GetDamageReductionRate(ObjShotID)
	- Returns the damage reduction rate specified in ObjShot_SetDamageReductionRate

###### [ph3.5 .1 pre6a open nf2]
 * Added "solid_pixel" tag to shot data definitions
	- In a shot data definition, if you add solid_pixel = true, the bullet will be rendered on solid pixels, preserving image quality.
 * Added SetTextureRenderMethod(Texture Width/Height determination)
	- Determines how future loaded textures' internal widths and heights are determined
 * Added ObjShot_SetEraseShotType(ShotObjID, behaviour)
	- When bullets are set to erase shots, their behaviour can be changed with this function.
 * Added ObjSpell_SetEraseShotType(SpellObjID, behaviour)
    - Sets the behaviour of ObjSpells when colliding with an enemy bullet
 * Added ObjMove_SetProcessMovement(ObjMoveID, process movement)
	- Determines whether the specified object will run their movement process or not.
 * Added ObjMove_GetProcessMovement(ObjMoveID)
	- returns the value that's specified in ObjMove_SetProcessMovement
 * Added SetShotDelayRenderBlendType(blend type)
    - Globally forces all delay clouds to use the specified blend type
 * Added GetShotDelayRenderBlendType()
    - returns the value that's specified in SetShotDelayRenderBlendType

 
 ## Changes To Master Branch
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
 * The exe will crash when trying to load a sound file that is both: not 1411kbs and is stereo
 
## Special Thanks
Natashi - for the code that made curvy lasers run a lot better than what I could do
</br>Trickysticks - for the woo art that graced the world
</br>UltimaOmega - for helping me with my sorry excuse for zlib code

## Contributions
This source is now closed for pull requests and modifications.  New features should go towards https://github.com/Natashi/Touhou-Danmakufu-ph3sx instead.

## License
zlib library has its own license, please check zlib.h in the repo for that information.</br></br>
(quoted from James7132's repo of the original source, maintaining the same license.) </br>This code is licensed under the NYSL (Niru nari Yaku nari Suki ni shiro License'). Main translated points:

 * "No warranty" disclaimer is explicitly included.
 * Modified version of the software MUST be distributed under the responsibility of the distributer.
 * Official version is written in Japanese.
