1. What are Channels and Kernels (according to EVA)?

   A kernel is a small matrix which is used to extract out differnt features of an image. Kernel operates upon the 2-d image matrix having pixel using simple mathematical operation to figure out the features of the image.All kernel posseses different characterstics based on the value they stores. Commonly used kernels in image processing are Edge Detection, Blurring, Sharpening , etc. Nomalised Kernel is one whose sum of all element equals 1.

   ![](https://docs.gimp.org/2.8/en/images/filters/examples/convolution-calculate.png)

   The above image shows the convolution of a 3x3 kernal.



2. Why should we only (well mostly) use 3x3 Kernels?

   A 3x3 kernel reduces the dimensions of the matrix by 2 on each side. Number of channels in output of 3x3 convolution is same as number of channel in 3x3kernel.

   ![](https://s3-ap-south-1.amazonaws.com/av-blog-media/wp-content/uploads/2018/12/Screenshot-from-2018-12-07-18-11-18.png)

    3x3 has significantly low data loss and is computationally economic in convolution as compared to other high dimensional convolutions, resulting the better efficiency of the model as slightly light features are not overshadowed by the loud features.

   ![](https://cdn-images-1.medium.com/max/600/1*1okwhewf5KCtIPaFib4XaA.gif)

   The no. of parameters also significantly decreses when we use multiple no of 3x3 kernel to make a big size kernel as compared to when we use a big size kernel itself. If we use a 11x11 kernel with 32 channels the no. of parameter calculation will be -

   (11x11)x32 = (121)x32 = 3872

   But if we use 5 3x3 kernel to make a 11x11 kernel , the parameter calculation will be-

   (3x3)x32+(3x3)x32+(3x3)x32+(3x3)x32+(3x3)x32 =

   9x32+ 9x32+ 9x32+ 9x32+ 9x32 = 9x32x5= 1440

   So there is significant difference between the no. of parameter in each case.

   

3. How many times do we need to perform 3x3 convolution operation to reach 1x1 from 199x199 (show calculations)?

    

   199x(3x3) |197x(3x3) |195x(3x3) |193x(3x3) |191x(3x3) |         [5] ( no of 3x3 convolution performed in the row)

   189x(3x3) |187x(3x3) |185x(3x3) |183x(3x3) |181x(3x3) |         [5]

   179x(3x3) |177x(3x3) |175x(3x3) |173x(3x3) |171x(3x3) |         [5]

   169x(3x3) |167x(3x3) |165x(3x3) |163x(3x3) |161x(3x3) |         [5]

   159x(3x3) |157x(3x3) |155x(3x3) |153x(3x3) |151x(3x3) |         [5]

   149x(3x3) |147x(3x3) |145x(3x3) |143x(3x3) |141x(3x3) |         [5]     

   139x(3x3) |137x(3x3) |135x(3x3) |133x(3x3) |131x(3x3) |         [5]

   129x(3x3) |127x(3x3) |125x(3x3) |123x(3x3) |121x(3x3) |         [5]

   119x(3x3) |117x(3x3) |115x(3x3) |113x(3x3) |111x(3x3) |         [5]

   109x(3x3) |107x(3x3) |105x(3x3) |103x(3x3) |101x(3x3) |         [5]

   99x(3x3) |97x(3x3) |95x(3x3) |93x(3x3) |91x(3x3) |                   [5]

   89x(3x3) |87x(3x3) |85x(3x3) |83x(3x3) |81x(3x3) |                   [5]

   79x(3x3) |77x(3x3) |75x(3x3) |73x(3x3) |71x(3x3) |                   [5]

   69x(3x3) |67x(3x3) |65x(3x3) |63x(3x3) |61x(3x3) |                   [5]

   59x(3x3) |57x(3x3) |55x(3x3) |53x(3x3) |51x(3x3) |                   [5]

   49x(3x3) |47x(3x3) |45x(3x3) |43x(3x3) |41x(3x3) |                   [5]

   39x(3x3) |37x(3x3) |35x(3x3) |33x(3x3) |31x(3x3) |                   [5]

   29x(3x3) |27x(3x3) |25x(3x3) |23x(3x3) |21x(3x3) |                   [5]

   19x(3x3) |17x(3x3) |15x(3x3) |13x(3x3) |11x(3x3) |                   [5]

   9x(3x3) |7x(3x3) |5x(3x3) |3x(3x3) |1					[4]



​	Total no of times we need to perform 3x3 convolution operation to reach 1x1 from 199x199 are-

​			19*5 + 4 = 95 +4 =99
