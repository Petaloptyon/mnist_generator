1) GAN_1 - first gan model; result: mediocre
How it works: 
  - train discriminator to distinguish real and fake images;
  - give random normal vectors to generator;
  - generator transform each vector into image and give it to discriminator;
  - discriminator define, is this image real or fake;
  - use backpropagation algorytm (during this process generator get information from discriminator, about features which it found) and, according with discriminator decision and change generator weights.

You can see prediction result of my model after 100 epochs. If I had more resources, I would continue to train the model further (perhaps result can become better).

![GAN_1_result](https://github.com/Petaloptyon/mnist_generator/assets/131547274/0881a6ac-15ad-43db-86ad-fe1891c5d46c)

1.1) I tried to add LayerNormalization to GAN_1. Here is the result of 85 epochs:

![GAN-1_with_Normalizationpng](https://github.com/Petaloptyon/mnist_generator/assets/131547274/d179534f-3aef-4ee1-b191-d49935248351)

1.2) I tried to add BatchNormalization to GAN_1. Here is the result of 150 epochs:

![image](https://github.com/Petaloptyon/mnist_generator/assets/131547274/c08cefe1-6500-425e-9c63-25c7fad1fe5b)

also i create a gif, using model predictions after each train epoch (for GAN_1 [1.2]):

![animation](https://github.com/Petaloptyon/mnist_generator/assets/131547274/0483d19b-2e84-4e13-856d-cb8a56c24a05)

conclusion: model overfitting too fast, and doesn't draw well



2) GAN_2 - i try to attach "uniqe noise" for each number (uniqe vector in latent space)

###################################### now i am working on improving model ######################################
