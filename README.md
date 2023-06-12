# Sobel
The program reads a bitmap image file, performs the Sobel edge detection algorithm on the image, and saves the result as a new bitmap file. The program uses structures to store the bitmap file header and info header, and defines a struct for RGB color values.

The `main` function is the entry point of the program. It prompts the user to enter the filename of the bitmap image to process.

1. The program opens the file using an `ifstream` in binary mode and checks if the file was opened successfully.
2. If the file is opened successfully, it proceeds to read the bitmap file header (`BITMAPFILEHEADER`) and info header (`BITMAPINFOHEADER`) using the `odczytajBFH` and `odczytajBFO` functions, respectively.
3. The program calculates the width and height of the image in pixels, taking into account any necessary padding.
4. Dynamic memory is allocated for a 2D array `tab` to store the RGB color values of each pixel in the image.
5. The `daneobrazka` function is called to display information about the bitmap file header and info header.
6. The `czytajobraz` function is called to read the RGB values of each pixel from the input file and store them in the `tab` array.
7. The `operatorsobel` function is called to perform the Sobel edge detection algorithm on the image data stored in the `tab` array. It uses pre-defined Sobel masks to calculate the gradient magnitude for each pixel.
8. The result of the edge detection is saved in separate 2D arrays `blue`, `red`, and `green` for the blue, red, and green color channels, respectively.
9. The memory allocated for `tab` is deallocated.
10. The program closes the input file and terminates.
