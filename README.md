# steganography-using-python
an image comprises of:
    ->Pixels are the building blocks of an image.
    ->Every pixel contains three values: (red, green, blue) also known as RGB values.
    ->Every RGB value ranges from 0 to 255.

Encoding:
   The algorithm is as follows:

   1.For each character in the data, its ASCII value is taken and converted into an 8-bit binary [1].
   2.Three pixels are read at a time having a total of 3*3=9 RGB values. The first eight RGB values are used to store one character                                        that is converted into an 8-bit binary.
   3.The corresponding RGB value and binary data are compared. If the binary digit is 1 then the RGB value is converted to odd and, otherwise, even.
   4.The ninth value determines if more pixels should be read or not. If there is more data to be read, i.e. encoded or decoded, then the ninth pixel changes to even. Otherwise, if we want to stop reading pixels further, then make it odd.
   
 Decoding:
   For decoding, we shall try to find how to reverse the previous algorithm that we used to encode data.

   1.Again, three pixels are read at a time. The first 8 RGB values give us information about the secret data, and the ninth value tells us whether to move forward or not.
   2.For the first eight values, if the value is odd, then the binary bit is 1, otherwise, it is 0.
   3. The bits are concatenated to a string, and with every three pixels, we get a byte of secret data, which means one character.
   4.Now, if the ninth value is even then we keep reading pixels three at a time, or otherwise, we stop.
