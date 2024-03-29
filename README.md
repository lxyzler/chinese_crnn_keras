## CRNN

Keras implementation of Convolutional Recurrent Neural Network for text recognition

There are two models available in this implementation. One is based on the original CRNN model, and the other one includes a spatial transformer network layer to rectify the text. However, the performance does not differ very much, so it is up to you which model you choose.


### Training

Data set: https://pan.baidu.com/s/1QkI7kjah8SPHwOQ40rS1Pw (password: lu7m)

A total of about 3.64 million images, divided into training and verification sets according to 99:1
The data is randomly generated by changes in font, size, grayscale, blur, perspective, and stretching using the Chinese corpus (news + classical Chinese).
Contains 5990 characters including Chinese characters, English letters, numbers and punctuation
Each sample is fixed with 10 characters, and the characters are randomly taken from the sentences in the corpus.
Image resolution is unified to 280x32

Run the `train.py` script to perform training, and use the arguments accordingly to your setup.

#### Execution example

```
python train.py --batch_size 512 --gpus 0 1 2 3 --nb_workers 12
```

You can resume training by setting `--resume_training` to True and defining the path to the model you want to resume training, `--load_model_path`.

A pretrained model is available [here](https://drive.google.com/file/d/1hmtbUQC5HuLb1KOMozNwCKFoAPa56rtx/view?usp=sharing).


### Evaluation

Use `eval.py` to perform evaluation. You can either classify a single image or pass a directory with images that you want to classify. You also have to specify the path to a trained model.





