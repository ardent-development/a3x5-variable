# a3x5-variable

The ultimate tiny raster font.

This font is designed for use in situations where text must be displayed in a grid of pixels extremely limited in resolution and density. It aims to be as legible as possible.

## Characteristics

 * Monospace
 * No ascenders or descenders: all characters fit between baseline and x-height
 * No intentionally decorative features
 * Character Size:
   * Width: 3 - 5 pixels, depending on complexity
   * Height: 5 pixels

## Character Set

Since the available canvas space is so limited, we can only implement so many characters. However, as this font is primarily meant to serve as the smallest available font on a scientific calculator, we can guarantee that there will be lots of mathematical symbols and Greek letters in the first release.

### Completeness

| Character Set              | Completeness |
| -------------------------- | ------------ |
| ASCII-7                    | 0/0 (0%)     |
| ASCII-8                    | 0/0 (0%)     |
| Greek letters              | 0/0 (0%)     |
| Mathematical symbols       | 0/0 (0%)     |

Take a look at [TODO.md](./TODO.md) for details.

### Handling of invisible control codes

The control code letters (BEL, NUL, etc.) are too big to fit within the 5x5 canvas space. So, control characters are expressed as such:
![The codes are represented as a 4x4 grid of 16 bits with the MSB at the top left and LSB at the bottom right.](./_md_assets/markers.png "The codes are represented as a 4x4 grid of 16 bits with the MSB at the top left and LSB at the bottom right.")

* The red shaded area is always white.
* The black shaded area is always black to signify that the character contains a control code.
* The rest of the area will contain the 16 bits that denote which control code is represented.
  * The topmost row is bits 0~3, left to right
  * The row below the topmost is bits 4~7
  * The row above the lowest is bits 8~11
  * The bottom row is bits 12~15
* The correspondence between each bit pattern and each control code is specified in [CONTROLCODES.md](./CONTROLCODES.md)

## Contributors

* twisted_nematic57
* fghsgh for her very insightful input and some contributions to the Greek letters

## Licensing

Public domain ;)
