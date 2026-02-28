# NeoEyes - Pixel Expressive Eyes Library
NeoEyes is an Arduino library to run a set of expressive eyes using either two 8x8 or one 8x16 Adafruit NeoPixel matric boards.

NeoEyes is a wrapper around a Fast LED matrix array, with in built expressive eye emotes, and the ability to also send custom eyes using a matrix template. It allows easy display of various expressive eyes such as happy or sad, as well as a blink functionality. 

The concepts, initial set of eye expressions, and an early prototype version were developed by [bucky17](https://github.com/bucky17) as part of the the work presented in "[Seeing Eye to Eye: Design and Evaluation of a Custom Expressive Eye Display Module for the Stretch Mobile Manipulator](https://doi.org/10.1109/ICRA55743.2025.11128312)." The Arduino library and extensible version were developed as part of [SAMI](https://github.com/shareresearchteam/SAMI-Robot) development by [Reakain](https://github.com/reakain).

## Operation
Install the library in your Arduino IDE through the Libraries Manager. Once installed, include it in your project.

## In-Built Expressions

| Appearance                        | Emote       | ID |
| --------------------------------- | ----------- | -- |
| <img src="res/.png" width="30%"/> | Off         | 0  |
| <img src="res/.png" width="30%"/> | Neutral     | 1  |
| <img src="res/.png" width="30%"/> | Happy       | 2  |
| <img src="res/.png" width="30%"/> | Sad         | 3  |
| <img src="res/.png" width="30%"/> | Angry       | 4  |
| <img src="res/.png" width="30%"/> | Confused    | 5  |
| <img src="res/.png" width="30%"/> | Closed      | 6  |
| <img src="res/.png" width="30%"/> | Sleepy      | 7  |
| <img src="res/.png" width="30%"/> | Dead        | 8  |
| <img src="res/.png" width="30%"/> | slightRight | 9  |
| <img src="res/.png" width="30%"/> | Right       | 10 |
| <img src="res/.png" width="30%"/> | slightLeft  | 11 |
| <img src="res/.png" width="30%"/> | Left        | 12 |
| <img src="res/.png" width="30%"/> | slightUp    | 13 |
| <img src="res/.png" width="30%"/> | Up          | 14 |
| <img src="res/.png" width="30%"/> | slightDown  | 15 |
| <img src="res/.png" width="30%"/> | Down        | 16 |

## Custom Expressions
A custom expression can be generated in one of two ways. The first is to send an 8x16 2D array of CRGB color values. This method is shown in the ```customExpression``` example.

The second is to send a custom emote.
An emote consists of two elements. The first is the color pallette, which identifies the colors that are displayed for the final matrix display. This includes LEDs that are turned off by denoting them as black in the pallette. The second element is an 8x16 2D array of ints, idenfitifying where each color goes in the physical LED matrix. This method is shown in the ```customEmote``` example.

Both methods are structued to allow designers to visually verify the designed expression matches what is sent to the controller.

## Additional Functionality
Beyond the expressions themselves, 

### Adjust the LED Brightness
You can adjust the overall brightness of the LEDs using the ```setBrightness()``` function. 
The usage example is ```setBrightness.ino```.

### Change the Color Palette
You can change the default color palette used by the standard emotes. You can either access it directly to change it, or use the ```setColorPalette``` class function. If you access the palette directly, you'll need to re-send the expression afterwards to make it refresh the color.

An example of using this functionality is in ```changeColorPalette.ino```.

### Color Objects
The named colors are referencing a predefined list from FastLED, available [here](https://fastled.io/docs/struct_c_r_g_b.html#aeb40a08b7cb90c1e21bd408261558b99). You can also make your own colors by declaring CRGB objects with hex values, such as ```CRGB(0xF0F8FF)``` which would be the same value as ```CRGB::AliceBlue```
