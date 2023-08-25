*`If you use my code, please attach a link to it, respect someone else's work`*

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
![animation](https://github.com/Petaloptyon/mnist_generator/assets/131547274/0483d19b-2e84-4e13-856d-cb8a56c24a05)

1.3) I complicate model and result becomes better, here is the result of 50 epochs.

![image](https://github.com/Petaloptyon/mnist_generator/assets/131547274/edd69540-3439-4dc1-bc99-45e6ed6ede6e)
![GAN_1 3](https://github.com/Petaloptyon/mnist_generator/assets/131547274/dab02d8d-1a8c-4cab-963d-8e38dcbba809)

I decided to modify GAN_1.3 so that it can generate any numbers on request. I use a list of 10 generators for each digit (zero g_model creates '0', first g_model creates '1'...) and build a dictionary of possible clues. When you write any numbers for this GAN, it will activate the corresponding g_models and give you the result.
For example, i gave this prompt: 248112985160145349571385 and got this back:

![image](https://github.com/Petaloptyon/mnist_generator_by_prompt/assets/131547274/126ecb2a-53e7-43b1-8328-bdcd3ae6cf72)

Here you can see the result of training each g_model after 150 epochs:

![GAN_1 4_requesting_gif_0](https://github.com/Petaloptyon/mnist_generator/assets/131547274/5d80d26b-2353-4953-be1f-448bcf78f754)
![GAN_1 4_requesting_gif_1](https://github.com/Petaloptyon/mnist_generator/assets/131547274/6755ae73-17d3-430b-ad97-dfa5a53de8c6)
![GAN_1 4_requesting_gif_2](https://github.com/Petaloptyon/mnist_generator/assets/131547274/ae4fa14b-e610-4aaf-bad5-f354135b9bb0)
![GAN_1 4_requesting_gif_3](https://github.com/Petaloptyon/mnist_generator/assets/131547274/df5c8223-257e-428b-a2f8-6e8ca1cbac15)
![GAN_1 4_requesting_gif_4](https://github.com/Petaloptyon/mnist_generator/assets/131547274/28c1a5be-dbad-4890-8cd5-ddd3270d8f17)
![GAN_1 4_requesting_gif_5](https://github.com/Petaloptyon/mnist_generator/assets/131547274/706de46e-8b07-40cf-a170-51509b40d89f)
![GAN_1 4_requesting_gif_6](https://github.com/Petaloptyon/mnist_generator/assets/131547274/9ab97b04-044e-4fa0-81c3-4dcd2636b5dc)
![GAN_1 4_requesting_gif_7](https://github.com/Petaloptyon/mnist_generator/assets/131547274/c8a6ba51-52a1-49af-8652-1bdc4ccbd423)
![GAN_1 4_requesting_gif_8](https://github.com/Petaloptyon/mnist_generator/assets/131547274/4f298a0a-8cd8-4dec-af98-192a76c8b2a3)
![GAN_1 4_requesting_gif_9](https://github.com/Petaloptyon/mnist_generator/assets/131547274/42a67a4d-c5a9-4646-ad12-66fc12e95880)

