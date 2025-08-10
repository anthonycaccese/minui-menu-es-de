# MinUI Menu for ES-DE

This is a translation of the MinUI menu interface (originally designed & created by [Shaun Inman](https://github.com/shauninman/)) for ES-DE.

My work focused on translating the layout so that it could be buildable in the theme engine for ES-DE.  Please refer to the `Changes Made` section below for additional details. 

The original version of the UI can be found as part of the awesome MinUI custom firmware [here](https://github.com/shauninman/MinUI).

## Changes Made

- Used [MinUI screenshots](https://raw.githubusercontent.com/shauninman/MinUI/main/github/minui-main.png) to approximate the components that would be used build a theme compatible with ES-DE.
- Changed the helpsystem to ES-DE's native component and created a layout that tries to evoke the original helpsystem design (sadly it can't be a 1:1 translation due to differences in the theme engines)
- Added icons and badges specific to ES-DE functionality
- Added a framework for adding additional color schemes and added Light and Dark options to start
- Added Bold and Non-Bold font options

## **Preview**

![Screenshot 2024-06-04 at 12 48 06 PM](https://github.com/anthonycaccese/miniui-menu-es-de/assets/1454947/b7d83e0c-c66d-41f0-bc78-5a8bc78ff3b5)

## **Configuration Options**

The theme has a simple set of options that can be changed directly from the UI Settings menu of ES-DE 

### **Variants:**

- `Theme Variant` - sets the color scheme that is used for the overall theme on all views.
   - `List` - The default color variant.  A simple list in the style of MinUI
   - `List + Boxart` - Adds the display of boxart to the list
   - `List + Cover` - Adds the display of screenshots to the list
 
| List | List + Boxart | List + Screenshot |
|----|----|----|
| ![List](https://github.com/anthonycaccese/minui-menu-es-de/assets/1454947/38d75de9-cd1f-4c07-9483-4d8d36b63e81) | ![List + Boxart](https://github.com/anthonycaccese/minui-menu-es-de/assets/1454947/30a8a4a1-4943-4f05-85f2-39334f75c286) | ![List + Screenshot](https://github.com/anthonycaccese/minui-menu-es-de/assets/1454947/80251c80-68b2-450b-ac3b-4562c8568caa) |

### **Color Schemes:**

- `Theme Color Scheme` - sets the color scheme that is used for the overall theme on all views.
   - `Dark` - The default color scheme. 
   - `Light` - A `light` version of the above color scheme.
 
| Dark | Light |
|----|----|
| ![Screenshot 2024-06-04 at 12 48 00 PM](https://github.com/anthonycaccese/miniui-menu-es-de/assets/1454947/35e60b4e-78b0-417f-bdc0-3c85e9c580e8) | ![Screenshot 2024-06-04 at 12 48 14 PM](https://github.com/anthonycaccese/miniui-menu-es-de/assets/1454947/63566ff2-6968-4f55-b8dc-a22a1e4a6b89) |

You can also create your own custom color scheme by following the instructions under "[Creating your own color scheme](https://github.com/anthonycaccese/minui-menu-es-de?tab=readme-ov-file#creating-your-own-color-scheme)"

### **Font Sizes:**

- `Theme Font Size` - sets the size that text will render at. This can be helpful when using the theme on small screens.
   - Supported Font Sizes:
   - `Medium` - Default size, good for small handheld screens under 6 inches in size.
   - `Large` - Good for small handheld screens under 4 inches in size.
   - `Small` - Smaller size, good for larger screens.
   - `Extra Large` - Good for small handheld screens under 4 inches in size.
   - `Extra Small` - Smaller size, good for larger screens.

### **Aspect Ratios:**

- `Theme Aspect Ratio` - sets the aspect ratio to match your display. This should happen automatically but can also be set manually if needed.
   - Supported Aspect Ratios:
   - `4:3`
   - `16:9`
   - `16:10`
   - `3:2`
   - `19.5:9`
   - `1:1`
 
## Additional Notes

### **Creating your own color scheme:**

1) In the resources folder you will find a template file called [colors-custom.xml](https://github.com/anthonycaccese/miniui-menu-es-de/blob/main/resources/colors-custom.xml)

2) Make a folder named `theme-customizations` and place a copy of the `colors-custom.xml` file inside that folder.  The folder structure should look like this when you are done:
   ```
   /ES-DE/themes/minui-menu-es-de/theme-customizations/colors-custom.xml
   ```
   *Note: This structure should allow you to continue to get updates for the theme from the theme downloader while also retaining your customizations.*

3) Edit the properites in `colors-custom.xml` to create your custom color scheme:
   - Here is a definition of each property:
      - `backgroundPath-{aspect ratio}` - Sets the path to an image to use for the background.  
         - If you want the background to be a solid color then you can populate this property with a value of `${spacerImage}` and then set the value for `backgroundColor` to the color you prefer.  
         - If you want to set this to a fullscreen image then add your image into the `theme-customizations` folder and set the value for this property to the path to your image.  For example; if your image was named `background.png` then the value you would set for this would be `./theme-customizations/background.png`.
         - You can choose to define a specific background image for each aspect ratio by defining a specific path for each.  You can also use the same image for all aspect ratios by defining this value the same for each.
      - `backgroundCropPos-{aspect ratio}` - Define how the background image should be positioned.
      - `backgroundTile` - Sets if the background image should be repeated (aka tiled) or not.  Allowed values are `true` or `false`
      - `backgroundColor` - Sets the color to be used for the background on all screens.  If you are using a fullscreen image its best to set this to `ffffff` so that the original image's colors will display.
      - `textlistFont` - The font that will be used for the system and game list.
         - If you want to use ES-DE's default font then you can set this value to `default`
         - If you want to use the MinUI font then you can set this value to `./_inc/fonts/BPreplayBold.otf`
         - If you want to use your own font then add your font file into the `theme-customizations` folder and set the value for this property to the path to your font.  For example; if your font was named `font.ttf` then the value you would set for this would be `./theme-customizations/font.ttf`.
      - `textlistSelectedColor` - Sets the text color for the selected item in the list
      - `textlistSelectedBackgroundColor` - Sets the highlight color for the selected item in the list
      - `textlistSelectedBackgroundCornerRadius` - Sets how round the corners of the selector should be. `0` will remove the rounded edges, `0.05` will make a pill shaped selector.  You can try different values inbetween for different effects.
      - `textlistUnselectedColor` - Sets the text color for unselected items in the list
      - `helpsystemFont` - The font that will be used to display text in the included help system.  
         - If you want to use ES-DE's default font then you can set this value to `default`
         - If you want to use the MinUI font then you can set this value to `./_inc/fonts/BPreplayBold.otf`
         - If you want to use your own font then add your font file into the `theme-customizations` folder and set the value for this property to the path to your font.  For example; if your font was named `font.ttf` then the value you would set for this would be `./theme-customizations/font.ttf`.
      - `textlistDisplaySystemSuffix` - allows you to turn the display of system suffix on or off in collections.  allowed values are `true` and `false`
      - `gameArtColor` - Applies a color shift to the game art. For example, an all-white image with FF0000 applied would become completely red. You can also control the transparency of the image by setting the value to for example FFFFFFAA. This keeps all pixels at their normal color and only affects the alpha channel. This property is applied after saturation so by setting that property to 0 it's possible to colorize rather than color shift.
      - `gameArtSaturation` - Controls the level of color saturation for the game art. Minimum value is `0` (grayscale) and maximum value is `1` (original file saturation).
      - `gameArtBrightness` - Controls the relative level of brightness for the game art. This is intended primarily for fine adjustments, for example if a color shift has been applied which may have lowered the overall brightness of the image.
      - `gameArtCornerRadius` - Sets how round the corners of the game art should be. `0` will remove the rounded edges.
      - `helpsystemLetterCase` - Sets the lettercase that is used for text in the included help system.  Allowed values are `lowercase`, `uppercase` or `capitalize`
      - `helpsystemIconColor` - Sets the icon color for items in the included help system
      - `helpsystemTextColor` - Sets the text color for items in the included help system
      - `badgeIconColor` - Sets the icon color for badges (Favorite, Completed, Collections, etc.) displayed on the gamelist view.
    
4) Set the `Theme Color Scheme` in ES-DE's UI Settings menu to `Custom` and you should see your custom color scheme display.  If you see an error check that the paths discussed above are correct and then check that the values you added for each property are correct and well formatted.

#### Examples:

Changing the values for each property should allow you to create any number of color schemes.  Here are a few examples that have been made using the same properties:

| "Pocket Micro" | "Pocket DMG" |
|:----:|:----:|
| ![Screenshot 2024-06-04 at 8 41 07 PM](https://github.com/anthonycaccese/miniui-menu-es-de/assets/1454947/3c0076e5-d575-4bcd-aae1-25863e2219d0) | ![Screenshot 2024-06-04 at 8 40 59 PM](https://github.com/anthonycaccese/miniui-menu-es-de/assets/1454947/bafbdec4-c60c-41e7-bda6-c86020a599bb) |
| "Fallout" | "Cyberpunk" |
| ![Screenshot 2024-06-28 at 9 48 28 AM](https://github.com/anthonycaccese/minui-menu-es-de/assets/1454947/4ec3504b-7000-4ad8-9264-9df0722e4fcd) | ![Screenshot 2024-06-28 at 9 48 19 AM](https://github.com/anthonycaccese/minui-menu-es-de/assets/1454947/bdbe8140-d62c-4906-8106-8425943bceb6) |

If you make a custom color scheme and are comfortable with sharing I would love to check it out 😊
- Please feel free to create an issue in this repo called `Custom Color Scheme: [Name of your Color Scheme]`
- Include the values you used for the properties above (xml is preferred), the background image and fonts you added (if any) and a screenshot of what it looks like.

## **Credits:**

- The original MinUI was created & designed by [Shaun Inman](https://github.com/shauninman/)
- The included font is called ["VAG Rounded Std"](https://fontsgeek.com/vag-rounded-std-font)
- The icons used to create the badges were sourced from [FontAwesome](https://fontawesome.com/search?o=r&m=free)
- User Created Color Schemes:
   - `Fallout` and `DMG` - Created and provided by [RobZombie9043](https://github.com/anthonycaccese/minui-menu-es-de/issues/2)
