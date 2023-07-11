You can see prediction result of my model after 100 epochs. If I had more resources, I would continue to train the model further (perhaps result can be better).
How it works: 
  - train discriminator to distinguish real and fake images;
  - give random normal vectors to generator;
  - generator transform each vector into image and give it to discriminator;
  - discriminator decide, is this image real or fake;
  - use backpropagation and, according with discriminator decision (during this process generator get information from discriminator, about features which it found) and change weights in generator.

###################################### now i am working on improving model ######################################
