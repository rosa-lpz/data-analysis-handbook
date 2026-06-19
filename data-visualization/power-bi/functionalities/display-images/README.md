
# Display higher solution image in Power BI

## Options
### Images in binary should be converted to text (base64)

Practical limits on the maximum length of a text value in Power BI
* the maximum length of a text value in Power BI: the 32766 character
* 2.1 million character limit in DAX function
Note
* Base64 makes files 33% larger

### Use public URL 
* Images in a azure blob with public read access. Then write the URL back to SharePoint SQL.

### Consideration

* There is not official documentation for first option 1 the solution is mainly based on the blog from Chris Webb

**Binary files**
Binary file of 1 million characters (zeros and ones) is exactly 123,000 bytes (or 125 KB) in physical data size.
Actual size depends entireyly on how is stored
* As raw bits (actual binary data)
    * Calculation:1,000,000 bits /8 bits per byte = 125,000 bytes
    * Standard Unit: Exactly 125 kilobytes (KB) (decimal) or roughly 122 Kibibytes (KiB) (binary)

* Stored as characters (string of text)
    * ASCII / UTF-8 Enconding: Most commom text forman use 1 byte per basic character
        * 1,000,000 chacaters X byte = 1,000,000 bytes (Exactly 1 MB)
    * UTF-16 Enconding: Many modern programming languages (like Java, C#, or Javascript) store text strings using 2 byets per character.
        * 1,000,000 characters x 2 bytes = 2,000,000 bytes (Exactly 2 MB)
    


# References
* https://www.reddit.com/r/PowerBI/comments/1nqvk8o/higher_resolution_dynamic_images/
* https://medium.com/@crisalexis3008/how-we-got-power-bi-to-display-large-images-stored-in-sql-as-binary-c807793cffdd
* https://blog.crossjoin.co.uk/2019/05/19/storing-large-images-in-power-bi-datasets/

## Videos
* A little trick for SharePoint Online Images in Power BI: https://www.youtube.com/watch?v=EowHdhy-Nio&pp=ygUPcG93ZXIgYmkgaW1nYWVz
* THE BEST way to add IMAGES from OneDrive & SharePoint in Power BI: https://www.youtube.com/watch?v=BxcHdwF7_1s
* IMPORT IMAGES into POWER BI // DIFFERENT WAYS to Import and Use Images in Power BI Reports
* Using IMAGES in Power BI: https://youtu.be/hGKykytzLXs
* Using Images from a Database in Power BI: ImaShowhttps://youtu.be/Q82yzcfkqAc 