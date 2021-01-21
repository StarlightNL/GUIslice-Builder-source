In this fork I will try to add the following functions:
- JSON import and export functionality to create a GUI with only text.
    The JSON will support "modules" that are pre made elements grouped together for fast repetitive parts of a gui.
- Control via serial port.
    This will be like the nextion displays. A gui running on a sepperate controller

# GUIslice Builder

Please refer to the wiki page for installation and usage details:

[GUIslice Builder - Documentation](https://github.com/ImpulseAdventure/GUIslice/wiki/GUIslice-Builder)

![image](https://user-images.githubusercontent.com/8510097/90728338-9a8be100-e279-11ea-969e-cbd8bb0ac6c6.png)

## Brief Overview
The GUIslice Builder is a standalone desktop application that is more than a layout tool for your UI. It's designed as 
No Code GUI Generator for User Interfaces that make use of GUIslice API. 

The cross-platform utility includes a WYSIWYG graphical editor that enables drag & drop placement of UI elements. Once a GUI has been laid out, the Builder can then generate a fully functional GUIslice Graphical UI complete with plug-in points for your custom application. 

The GUIslice API framework code can handle hardware like Arduino, ESP8266, ESP32 and more. It supports Graphic libraries like 
Adafruit's GFX, M5Stack, TFT_eSPI and LINUX with a wide variety of TFT Display Drivers and combinations of Touch support chips.

The generated output code (*.c, *.ino, *_GSLC.h) includes all of the necessary defines, UI storage elements and initialization 
in addition to the placement of the UI elements. This will greatly improve the ease in creating a new Graphical Application.

You can find Example project files inside GUIslice/examples/builder

<<<<<<< HEAD
## Disclaimer ##
The Software is not designed for use in devices or situations where there may be physical injury if the Software has errors.

## Builder Contents
Note that the Builder executables and User Guide are attached to the latest GUIslice Builder Repository [Release Notes](https://github.com/ImpulseAdventure/GUIslice-Builder/releases):

## Builder Source Code
The Builder source code is located in this repository [ImpulseAdventure/GUIslice-Builder](https://github.com/ImpulseAdventure/GUIslice-Builder)
- Build instructions can be found in `BUILD.txt`

## Release History

### Enhancements for 0.16.0

With this release the Builder becomes a true WYSIWYG editor for most platforms. The Builder now reads and parses 
your actual Platform Font header and c files and renders them inside the Builder. This native font support will now 
be able to give you accurate sizing and positioning information for supported fonts. Plus your text will be now 
displayed exactly as it will appear on your target TFT display. 

The Native Font support includes, Adafruit's Builtin GLCD fonts, and Adafruit's GFX compatable fonts, and 
Teensy ILI9341_t3 fonts. This Native Font support includes the ability to add your own fonts to the Builder 
simply by dropping them into the proper folders. You may also tell the Builder to simulate fonts it doesn't directly support. 

See the User Guide for more information about font handling and how to add your custom fonts.

GUIslice API 0.16.0 has upgraded the Keypad support. This is a breaking change for the API so the Builder 
will now require running with GUIslice API 0.16.0 and higher. For further information on keypads 
refer to the wiki page [Custom KeyPads](https://github.com/ImpulseAdventure/GUIslice/wiki/Custom-KeyPads)

The Builder has added support for ctrl-Z for Undo and ctrl-Y for Redo.

### Enhancements 0.16.b006
Added support for TFT_eSPI smoothfonts (*.vlw). Google's Dosis Bold and NotoSans Bold is built in. 

You may add your own vlw fonts by following the updated User Guide chapter 5.7 Adding Fonts and Appendix G Creating VLW Fonts.

### Bug Fixes 0.16.b006
 - Bug No. 205 No CallBack from Checkbox using Flash API issue `#347` 

### HotFix for 0.16.b005
 - Bug No. 204 Crash  occurs while selecting NotoLatin1 when size of font is > 28 issue `#143`
 - Bug No. 203 Box using Flash API can't do code gen for Draw callback
 - Bug No. 202 Draw function selected for Box frame the rounded property should be disabled API issue `#326`

### Enhancements for 0.16.b004
Added CharacterMap dialog to "Text" propery fields for UIElements Text, Text Button, Text Input, Spinner, and Number Input.

This feature will allow you access to graphics characters previousily hidden in Adafruit's classic (Builtin) fonts and other fonts. 
You can also access ISO8859 international characters using a newly added NotoLatin1 font.

First set your desired font then invoke CharacterMap by right clicking on the "Text" property and selecting CharacterMap. 
Select your characters one at a time and then press copy to append them to your text field.

The User Guide has been updated documenting this new feature.  

The UI Element Spinner has been upgraded to support changing the Increment and Decrement Arrow characters using the API call gslc_ElemXSpinnerSetChars().


### Bug Fixes 0.16.b004
 - Bug No. 201 Text button frame cannot be disabled issue `#139`

### HotFix 0.16.b003
 - Bug No. 200 New Keypad support causes input field button case-statement to be deleted and recreated
 - Bug No. 199 Sizing of rect for Text with margin doesn't include space on right-side

### HotFix 0.16.b002
GUISlice crashing after clicking generate code issue `#134`
- Bug No. 198 Assigning storage to text field gives incorrect height API issue `#292`

### HotFix 0.16.b001
 - Bug No. 197 Crash opening project with screen larger that 320x240
 - Bug No. 196 Dup gslc_ElemSetTxtCol when text not set to the default color

### Bug Fixes 0.16.0
 - Bug No. 195 Enhancement - Add Top/Bot to Text Button text alignment fields `#127`
 - Bug No. 194 gslc_GetImageFromRAM creates const pointer issue `#126` 
 - Bug No. 193 codegen fails to work for GSLCX_CHECKBOX_STYLE_ BOX or ROUND issue `#128`
 - Bug No. 191 Crash if slider min=max
 - Bug No. 189 Add shortcut ctrl+z for UnDo
 - Bug No. 187 App window not controllable with Java built-in themes issue `#112`
 - Bug No.  98 Text element "Fill Enabled=false" doesn't render with transparency

=======
### Release History

#### Changes for 0.13.0.2 Hot Fix for projects created with early beta versions of the builder

##### Bug Fixes
 - Bug No. 102 crash running code generation due to missing tags in .ino or .c files for older projects
 - Bug No. 103 Upgrading older project files causes duplicate storage to be assigned
 
#### Changes for 0.13.0.1 Hot Fix for linux and mac/os

##### Bug Fixes
 - Bug No. 100 Linux target platform gives missing FONT_INCLUDE template 
 - Bug No. 101 Builder fails to load in mac/os can't find starting class

#### Changes for 0.13.0

### Known Issues for Release 0.13.0

 - Bug No. 48 Crash on generate code in macOS when space in file name. 
 - Bug No. 86 Need to double click mouse twice sometimes to get a selection.
 - Bug No. 91 Fails to trap "invalid" filenames that are not permitted by the Arduino IDE

##### New UI Elements Supported

 - Line
 - Listbox
 - Number Input
 - Radial Gauge
 - Ramp Gauge
 - Ring Gauge
 - Spinner
 - Text Input
 - Base Page
 - PopUp Dialog Page
 
#### Removed Features
 - Import Button for importing non-builder created projects. Round trip edits of builder created files are still supported. Maintence costs for the Import feature were too high to continue support.

##### Bug Fixes
 - Bug No. 7  Support transparency in BMP 
 - Bug No. 12 All widgets should allow renaming ElementRef field
 - Bug No. 27 Ability to duplicate an elements 
 - Bug No. 65 Creating saved ElemRef should follow ElemCreate instead of using PageFindElemById
 - Bug No. 66 XTextBox bad values sent to the gslc_ElemXSliderCreate() 
 - Bug No. 68 Regenerating code increments m_sX* array indices in ElemX*Create()
 - Bug No. 69 Box UI for tick func generates gslc_ElemSetTxtAlign() instead of gslc_ElemSetTickFunc()
 - Bug No. 70 Code gen puts out gslc_ElemCreateBox instead of gslc_ElemCreateBox_P version for arduino flash
 - Bug No. 71 Code gen for XGraph crashes 
 - Bug No. 72 remove Auto gen id in arduino flash _P routines 
 - Bug No. 73 remove save folder restrictions
 - Bug No. 75 Widget select+move sometimes unresponsive
 - Bug No. 76 Image file selection always opens to arduino_res Remember last directory in which an image was selected
 - Bug No. 77 Changed global option Target Image Directory isn't retained without pressing Enter first before OK 
 - Bug No. 79 Added status bar to avoid confirmation dialogs 
 - Bug No. 80 Deleting a Button Image does not remove the corresponding case in the CbBtnCommon callback function.
 - Bug No. 81 Extended widgets headers no longer use GUIslice_ex.h 
 - Bug No. 82 keyboard shortcutsfor the frequently used System related functions (Save Export Delete etc.). 
 - Bug No. 83 request to resize panes 
 - Bug No. 85 grouping radio buttons always assigns GROUP0 
 - Bug No. 87 Crtrl-D is supported for deletions but not Command Delete key
 - Bug No. 88 Default target image path needs leading slash “/“ on SD filenames
 - Bug No. 89 Element drag when in zoomed mode doesn't track mouse 
 - Bug No. 90 checkboxes and radio buttons should have either width or height. 
 - Bug No. 92 Change the default background color to black 
 - Bug No. 96 Fatal error can cause crash log loop 
 - Bug No. 97 Install not change project directory
 - Bug No. 99 Progress Bar Frame not showing up on TFT simulation screen
 
>>>>>>> master
