# tensorflow-basic-CNNs
Some of the problems I had when I ran code from GitHub on the server
the father project is https://github.com/calmisential/Basic_CNNs_TensorFlow2
when i use his code to train my own dataset,there is a problem:
The Conc2d op currently does not support grouped convolutions on GPUS.A groups convolution was attempted to be run because the input depth of 32 dose not match the filter input depth of 16



I tried hard to find where is the problem. All my changes to the program are limited to saving addresses and datasets

After a while I found out what was wrong.
111 lines in train.py gpus = tf.config.list_physical_devices("GPU"),THE GPU is diferent from what was setting in the config.py
so i change it into gpus = tf.config.list_physical_devices("gpu")
