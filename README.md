# MinUI Menu for ES-DE

This is a tranlation of the MinUI menu interface (originally designed & created by [Shaun Inman](https://github.com/shauninman/)) for ES-DE.

My work focused on tranlating the layout so that it could be buildable in the theme engine for ES-DE.  Please refer to the `Changes Made` section below for additional details. 

The original version of UI can be found as part of the awesome MinUI custom firmware [here](https://github.com/shauninman/MinUI).

## Changes Made

- Used [MinUI screenshots](https://raw.githubusercontent.com/shauninman/MinUI/main/github/minui-main.png) to approximate the components that would be used build a theme compatible with ES-DE.
- Changed the helpsystem ES-DE's and created a layout that tries to evoke the original helpsystem design (sadly it can't be a 1:1 translation due to differences in the theme engines)
- Added icons and badges specific to ES-DE functionality
- Added a framework for adding additional color schemes and added Light and Dark options to start
- Added Bold and Non-Bold font options

## **Preview**

![Screenshot 2024-06-04 at 12 48 06 PM](https://github.com/anthonycaccese/miniui-menu-es-de/assets/1454947/b7d83e0c-c66d-41f0-bc78-5a8bc78ff3b5)

## **Configuration Options**

The theme has a simple set of options that can be changed directly from the UI Settings menu of ES-DE 

### **Color Schemes:**

- `Theme Color Scheme` - sets the color scheme that is used for the overall theme on all views.
   - `Dark` - The default color scheme. 
   - `Light` - A `light` version of the above color scheme.
 
| Dark | Light |
|----|----|
| ![Screenshot 2024-06-04 at 12 48 00 PM](https://github.com/anthonycaccese/miniui-menu-es-de/assets/1454947/35e60b4e-78b0-417f-bdc0-3c85e9c580e8) | ![Screenshot 2024-06-04 at 12 48 14 PM](https://github.com/anthonycaccese/miniui-menu-es-de/assets/1454947/63566ff2-6968-4f55-b8dc-a22a1e4a6b89) |

### **Font Sizes:**

- `Theme Font Size` - sets the size that text will render at. This can be helpful when using the theme on small screens.
   - Supported Font Sizes:
   - `Medium` - Default size, good for small handheld screens under 6 inches in size.
   - `Large` - Good for small handheld screens under 4 inches in size.
   - `Small` - Smaller size, good for larger screens.

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

### **Create a custom color scheme:**

Coming Soon

### **Credits:**

- The original MinUI was created & designed by [Shaun Inman](https://github.com/shauninman/
- The font used is called "BPreplay" and was created by [George Triantafyllakos](https://backpacker.gr/)
- The icons used to create the badges were sourced from [FontAwesome](https://fontawesome.com/search?o=r&m=free)