# IMAGE TO ASCII ART

Create a text document containing the ASCII representation of any given image.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

## Description

This program takes an image and produces a copy of it made entirely of [ASCII]
printable characters; this copy can, therefore, be stored in a plain text file.

The idea is to take each pixel of the input image and, according to its
brightness value, map it to a different character.  
*Smaller* characters like ```.``` or ```:``` are mapped to the brighter areas of
the image, while *bulkier* ones like ```@``` or ```#``` will be used to
represent the shadows. (this behaviour can be [changed])

The user can choose their own list of characters, I copied it from [here].

**NOTE:**
The text will only form a recognizable shape if displayed with a [monospaced
font].

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

## Example Result

Below are shown a sample image and its text version side by side:

![demo_image]
![demo_ascii]

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

## Usage

Clone or [download] this project and *cd* into its root directory.

Launch the program with the following command:

```shell
python ascii.py path/to/image
```

If no path to an image file is specified via command line argument the program
will try to open one of the sample images in the *data/* directory.

### Parameters

A few parameters have default values that can be changed inside the [main file].

#### ASCII FILE PATH

Path to the text file in which to write the output.

#### OUTPUT WIDTH

Width for the ASCII text; intended as the maximum number of characters per line.  
Based on this value, a corresponding *height* is calculated in order to preserve
the original aspect ratio.

Set this value to ```0``` to **not** alter the input size.

Having a bigger "canvas" leads to a clearer image, with more details; the
downside is that it would take a rather small font size to be able to display
the picture in its entirety.

#### SEQUENCE

Array of characters to map to the image's pixels.  
The characters **must** be sorted from lowest to highest "level of brightness".

#### PRODUCE NEGATIVE

This boolean value, when set to ```True```, will produce a negative version of
the image, mapping the "higher value" characters of SEQUENCE to the darker
areas of the picture.

It should only be ```True``` when displaying black text on a light background.

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

## Dependencies

+ python 3.6+
+ **PIL** module  
can be installed with the following command:

    ```shell
    pip install pillow
    ```

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

## Author

Marco Plaitano

- - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - - -

## License

Distributed under the [MIT] license.

<!-- LINKS -->

[ASCII]:
https://theasciicode.com.ar/

[changed]:
#produce-negative
"Anchor to header"

[here]:
http://paulbourke.net/dataformats/asciiart/

[monospaced font]:
https://en.wikipedia.org/wiki/Monospaced_font

[demo_image]:
https://github.com/marcoplaitano/images/blob/main/image_to_ascii_demo_image.png
"Sample image PNG version"

[demo_ascii]:
https://github.com/marcoplaitano/images/blob/main/image_to_ascii_demo_ascii.png
"Sample image ASCII version"

[download]:
https://github.com/marcoplaitano/image-to-ascii-art/archive/refs/heads/master.zip
"ZIP Download"

[main file]:
ascii.py
"Repository file"

[MIT]:
LICENSE
"Repository file"
