Previous work : https://github.com/SngJn-Ch/SR_gan 

# Piece_sr_gan
since current **hardware** only can handle 32 by 32 images, divide the large image into 32 by 32 image pieces and make each pieces into 64*64. By doing this, the final image will have 4 time higher resolution than the input images while it is not affected by the image size restriction.


# Key difference
- By resizing image of 256 by 256, the code can produce 32 by 32, 64 by 64, 96 by 96 ... and upto 256 by 256.
- For the images that are larger than 32 by 32, the code will divide that images into 32 by 32 pieces each
  - For example, a image with resolution of 128 by 128 become 16 pieces of 32 by 32 images
  - The image should be size of 32 * n

# Advantages
  1. Data Augmentation
    - One single piece of 256 by 256 images can generate 204 piece of 32 by 32 images
  2. higher resolution within limited hardware resource
    - Currently using google Colab Pro and can't handle image of 128 by 128 using a same layer
  3. Detail Training
    - The generator can train more detail of the input images

# Future Improvement
  1. Since the large images are assmebled images, some of the images have lattice pattern.
    - Adding average pixel lattice pattern
      - If the pixel at the left is (0.5, 0.25, 0.8) and the pixel at the right is (0.6, 0.35, 0.9) the pixel at the lattice pattern will be changed into (0.55, 0.3, 0.85)
      - Fluent change in pixel
     
  2. Currently only 4 times higher resolution
    - Applying different GAN technique and achieve more 16 times higher resolution

# Result

Left = Input image

Middle = Output Image

Right = Original Image



![380](https://user-images.githubusercontent.com/111392592/188997156-45efc977-5e1a-432a-a47d-001f02d63147.png)
![2478](https://user-images.githubusercontent.com/111392592/189972615-1177e343-d4d9-4dc4-8439-6d914dc643cb.png)
![2488](https://user-images.githubusercontent.com/111392592/189972625-e3d0ce01-5731-4e41-928f-a566e8eda6ad.png)
![2492](https://user-images.githubusercontent.com/111392592/189972637-c16c0760-5cee-4e62-9cba-69a09a5a8b3f.png)



# Reference

Previous Work

https://github.com/SngJn-Ch/SR_gan 

Paper

https://arxiv.org/pdf/1609.04802v5.pdf 

Data

https://www.image-net.org/download.php
