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
An expression consists of two elements. The first is the color pallette, which identifies the colors that are displayed for the final matrix display. This includes LEDs that are turned off by denoting them as black in the pallette. The second element is a 2D array of ints, idenfitifying where each color goes in the physical LED matrix. This allows designers to visually verify the designed expression matches what is sent to the controller.

Within the library is an example of sending a custom expression, labeled as customEmote.
