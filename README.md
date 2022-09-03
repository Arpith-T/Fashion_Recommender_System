### PRE-REQUISITES:
1. Deep Learning will be used here.
    * CNN - Convolution Neural Network
2. TRANSFER LEARNING.
    * Here we will be using already `existing models`. which are `trained`.
    * We wil be using `ResNET`, which is trained on `imageNET` dataset.
    * Hence, here, we will not be training any model.

## APPROACH:
### 1. Importing a model
* We wil be using `ResNET`, which is trained on `imageNET` dataset.
* This is a `builtin` model in `Keras`.
* this has a very high `Accuracy`.
* we wont be training our own model here as its time consuming an we will not be able to reach as high of an accuracy as ResNET already is.
* The `ResNET`mmodel will be used to `Extract Features`. which is our 2nd step.

### 2. Extract Features
* What do we mean by `Feature Extraction`?
    * we have 44k images. in our recommender system , we take a single image and compare it with 44k images. and we will recommed 5 images out of 44k images which is close to the image that we load.
    * For this to work, we need to analyze all the 44k images. which is expensive computationally.as there are 44k images, each with 224*224*3 pixel. 3 here refers to  (RGB)
    * So, from every image we extract features and we compare these features with our image.
    * > We will NOT be doing pixel to picel comparison between the products. But, Feature to Feature comparison
    * CNN here is used for Feature Extraction.
    * `ResNET` model wil give us the set of `2048 numbers` for every image that we pass. `2048` are the number features that this model will generate.
    * We have 44k images and 2048 features for each image.
    * we have 2D array for (44k, 2048)
    * Each image will have 2048 features. each row is a `vector` with 2048 Dimension. So, we have ``44k vectors``.
    * when we pass a new image to the ResNET model, it generates 2048 fetures and we map it in the co-ordinate system of 2048D space.
    * we have 44k vectors alredy here, when we plat new vector here in the model. `We simply recommend the closest vectos`