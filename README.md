# PlayerTextDrawStreamer


## Introduction

By default, SA-MP allows servers to create just 256 player textdraws per player. Many scripters, including myself have run into the issue of hitting that limit. While attempting to solve the issue, I found an old include created by theYiin that he had created for the same reason. Due to the include being abandoned and having many issues, I had to make many changes to it and now I've decided to release it give something back to the community.


## Dependencies

* [foreach](https://github.com/karimcambridge/SAMP-foreach) - Used to keep track of the player textdraw slots used and to iterate through them.


## Usage

The include is completely plug & play. Simply include the file in your script (`#include <PlayerTextDrawStreamer>`) and your player textdraw limit has magically\* been doubled.

The new limit of player textdraws has been set to 512 by default. If you wanna change it, simply define `MAX_PLAYER_TEXTDRAWS` with your own value **before** including PlayerTextDrawStreamer.

\* - The player textdraws are only created when they are visible on the player's screen. 


## Functions

The following functions are added by the include and are completely compatible with YSF when it's also being used.

```pawn
native IsValidPlayerTextDraw(playerid, PlayerText:text);
native IsPlayerTextDrawVisible(playerid, PlayerText:text);
native PlayerTextDrawGetString(playerid, PlayerText:text, string[], len = sizeof(string));
native PlayerTextDrawGetLetterSize(playerid, PlayerText:text, &Float:x, &Float:y);
native PlayerTextDrawGetTextSize(playerid, PlayerText:text, &Float:x, &Float:y);
native PlayerTextDrawSetPos(playerid, PlayerText:text, Float:x, Float:y);
native PlayerTextDrawGetPos(playerid, PlayerText:text, &Float:x, &Float:y);
native PlayerTextDrawGetColor(playerid, PlayerText:text);
native PlayerTextDrawGetBoxColor(playerid, PlayerText:text);
native PlayerTextDrawGetBackgroundCol(playerid, PlayerText:text);
native PlayerTextDrawGetShadow(playerid, PlayerText:text);
native PlayerTextDrawGetOutline(playerid, PlayerText:text);
native PlayerTextDrawGetFont(playerid, PlayerText:text);
native PlayerTextDrawIsBox(playerid, PlayerText:text);
native PlayerTextDrawIsProportional(playerid, PlayerText:text);
native PlayerTextDrawIsSelectable(playerid, PlayerText:text);
native PlayerTextDrawGetAlignment(playerid, PlayerText:text);
native PlayerTextDrawGetPreviewModel(playerid, PlayerText:text);
native PlayerTextDrawGetPreviewRot(playerid, PlayerText:text, &Float:fRotX, &Float:fRotY, &Float:fRotZ, &Float:fZoom);
native PlayerTextDrawGetPreviewVehCol(playerid, PlayerText:text, &color1, &color2);
```


## Notes

* Other SA-MP limits still apply to player textdraws: 
	* Only 256 player textdraws can be displayed at once per player. 
	* Textdraw strings are limited to 1024 characters. Color codes can't be used beyond the 255th character.
* In case YSF is used alongside PlayerTextDrawStreamer, YSF must be included **before** PlayerTextDrawStreamer.


## Credits

* **theYiin** - The original author of the include.
* **kvann** - The current maintainer.
