# Layer Batch Switching AviUtl Plugin

A plugin that enhances mouse operations for layers, allowing multiple layers to be toggled visible/invisible at once through drag operations.

[Download here.](https://github.com/AviUtl-EN-Translation/aviutl_toggle_layers_EN/releases)

<img src="https://github.com/user-attachments/assets/711e5afe-2f6b-4dc1-9d3e-1ac6e593c065"  height="600"/>

https://github.com/user-attachments/assets/98b5af15-93f1-4670-817e-d26e1d148987

https://github.com/user-attachments/assets/9f1be805-9476-4b1e-bdbd-bd36489bb89d


## Requirementー

- AviUtl 1.10 + Extended Editing 0.92

  https://hapsung.tistory.com/24

  - Does not work with other versions like Extended Editing 0.93rc1.
  - Except for the English version of the link above (WebCam's version), it doesn't work with any other version.

- Visual C++ Redistributable Package (x86 version for [2015/2017/2019/2022] required)

  https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170

- **(Recommended)** patch.aul r43 Nazo Sauna fork version 60 or later

  https://github.com/AviUtl-EN-Translation/patch.aul_en

  - Fixes issues where layer names may become incorrect after repeated layer drag moves and name changes followed by "undo".

## Installation

Copy `toggle_layers.auf` and `toggle_layers.ini` to one of the following folders:

1. The folder where `aviutl.exe` is located
1. The `plugins` folder within the folder from (1)
1. Any folder within the folder from (2)


## Usage

By default, the following operations are available (make sure to release any modifier keys other than those specified):

- Left-click drag on the layer button on the left side of the timeline to toggle the visibility of all layers passed by the cursor.

- `Shift` + left-click drag to toggle lock/unlock of layers passed by the cursor.

- `Ctrl` + left-click drag to select/deselect objects on layers passed by the cursor.

- `Alt` + left-click to display a dialog to change the name of the layer at the cursor position.

- Double left-click to toggle visibility of all other layers (executes "Show/Hide All Other Layers" from the right-click menu).

By editing the [configuration file](#configuration-file), you can use the following operations. Assign these to combinations of modifier keys and drag/double-click drag:

- Toggle "Coordinate Link" for layers passed by the cursor.

- Toggle "Clip with Upper Object" for layers passed by the cursor.

- Drag the entire content of a layer up or down.


## Configuration File

By editing the `toggle_layers.ini` file with a text editor, you can assign actions to key combinations and mouse operations. Refer to the comments in the file for detailed settings.

- The object selection feature via drag only works with combinations including the `Ctrl` key due to the specifications of Extended Editing.


## TIPS

- When dragging, if the mouse cursor goes beyond the top or bottom edge of the timeline window, it will scroll.

- As long as `Ctrl`, `Shift`, `Alt` are pressed when starting the drag, you can release them during the drag. However, releasing `Ctrl` will temporarily deselect objects.

- Even if an operation is assigned to double-click, the action for single-click will still execute. If you want to disable the single-click action, edit the configuration file and assign "Do nothing at all" to the respective item.


## Known Issues

- After repeated layer drag moves and name changes followed by "undo", layer names may not revert correctly or may change to completely different names. This can be fixed by using [patch.aul r43 Nazo Sauna fork version 60 or later](https://github.com/AviUtl-EN-Translation/patch.aul_en).

## Change Log

- **v1.61** (2024-06-08)

  - Fixed a bug where dragging an entire layer in a non-root scene did not move layer names and other settings, instead causing movement in the root scene.

- **v1.60** (2024-06-07)

  - Extended to allow assignment of operations to double-click and double-click drag.

    Added a `[double_click]` section to the configuration file. Change assignments in this section. If you want to inherit settings, refer to the included `.ini` file and add the necessary entries.

    - Initially assigned to "Show/Hide All Other Layers".

  - Improved auto-scroll behavior when dragging the mouse beyond the display range. Scrolling continues even without moving the mouse.

  - Made it possible to set auto-scroll enable/disable and speed.

    Added a `[scroll]` section to the configuration file. Change settings in this section. If you want to inherit settings, refer to the included `.ini` file and add the necessary entries.

- **v1.50** (2024-06-06)

  - Added a feature to drag the entire content of a layer up or down.

  - Slightly changed the specification of the configuration file. Changed `[key_combination]` at the beginning of the file to `[drag]`.

    **If inheriting settings from v1.40, change this initial part.**

  - Fixed an issue where "undo" did not function correctly if the edit state changed via shortcut commands during drag. Now the drag operation is canceled if an edit state change is detected.

  - Fixed the issue where the edit screen did not update for "Show/Hide All Other Layers".

- **v1.40** (2024-06-04)

  - Made it possible to configure the combination of modifier keys and layer operations via the `.ini` file.

  - Added operations for layers:

    1.  Toggle "Coordinate Link"
    1.  Toggle "Clip with Upper Object"
    1.  Show/Hide all other layers

- **v1.30** (2024-06-04)

  - Added a feature to display a dialog to change the layer name via `Alt` + click.

- **v1.20** (2024-05-31)

  - Added a feature to select/deselect objects on layers via `Ctrl` + drag.

- **v1.12** (2024-05-30)

  - Fixed layer number range check.

- **v1.11** (2024-05-30)

  - Fixed unnecessary redraw of the edit image when locking/unlocking layers.

- **v1.10** (2024-05-28)

  - Added a feature to lock/unlock layers via `Shift` + drag.

- **v1.02** (2024-04-26)

  - Code cleanup and minor improvements in functionality.

- **v1.01** (2024-04-26)

  - Changed to prevent layers outside the scroll range from being affected when the cursor is moved far outside the window during drag.

- **v1.00** (2024-04-26)

  - Initial release.


## License

This program is licensed under the MIT License.

---

The MIT License (MIT)

Copyright (C) 2024 sigma-axis

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the “Software”), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED “AS IS”, WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.

https://mit-license.org/


#  Credits

##  aviutl_exedit_sdk

https://github.com/ePi5131/aviutl_exedit_sdk

---

BSD 1-Clause License

Copyright (c) 2022
ePi All rights reserved.

Redistribution and use in source and binary forms, with or without modification, are permitted provided that the following conditions are met:

Redistributions of source code must retain the above copyright notice, this list of conditions and the following disclaimer.
THIS SOFTWARE IS PROVIDED BY ePi “AS IS'' AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL ePi BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.

#  Contact / Bug Reports

- GitHub: https://github.com/sigma-axis
- Twitter: https://twitter.com/sigma_axis
- nicovideo: https://www.nicovideo.jp/user/51492481
- - Misskey.io: https://misskey.io/@sigma_axis
- Bluesky: https://bsky.app/profile/sigma-axis.bsky.social
