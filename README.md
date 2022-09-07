Previous work : https://github.com/SngJn-Ch/SR_gan 

# Piece_sr_gan
since current **hardware** only can handle 32 by 32 images, divide the large image into 32 by 32 image pieces and make each pieces into 64*64. By doing this, the final image will have 4 time higher resolution than the input images while it is not affected by the image size restriction.


# Key difference
- By resizing image of 256 by 256, the code can produce 32 by 32, 64 by 64, ... and upto 256 by 256.
- For the images that is larger than 32 by 32, divide that image into 32 by 32 pieces
  - For example, image with resolution of 128 by 128 become 16 pieces of 32 by 32 images

# Advantages
  1. Data Augmentation
    - One single piece of 256 by 256 images can generate 204 piece of 32 by 32 images
  2. higher resolution within limited hardware resource
    - Currently using google Colab Pro and can't handle image of 128 by 128 using a same layer

# Future Improvement
  1. Since the large images are assmebled images, some of the images have lattice pattern.
    - Adding average pixel lattice pattern
  2. Currently only 4 times higher resolution
    - Applying different GAN technique and achieve more 16 times higher resolution

# Result

Left = Input image
Middle = Output Image
Right = Original Image


![380](https://user-images.githubusercontent.com/111392592/188997156-45efc977-5e1a-432a-a47d-001f02d63147.png)
![378](https://user-images.githubusercontent.com/111392592/188997962-10c3912e-2fbf-4c28-abcb-2fc79abde17b.png)


# Reference

Previous Work

https://github.com/SngJn-Ch/SR_gan 

Paper

https://arxiv.org/pdf/1609.04802v5.pdf 

Data

https://www.image-net.org/download.php
