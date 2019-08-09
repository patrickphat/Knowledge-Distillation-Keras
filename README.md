# Distilling knowledge in Neural Network

![img](img/knowledge-distillation.png)

The term **"Knowledge Distillation"** (a.k.a Teacher-Student Model) was first introduced by (Bu-cilu et al., 2006; Ba & Caruana,2014) and has been popularized by (Hinton et al., 2015), as a way to let smaller deep learning models learn how bigger ones generalize to large datasets, hence increase the performance of the smaller one.

In this notebook I'll show you an intuitive way on how you can implement Knowledge Distillation in Keras. 

In this notebook:

- I use the CIFAR10 dataset from tf.keras.datasets
- I use Colab Notebook's K80 GPU for training (which save a lot of time & money..)
- I use Keras as a high-level API of Tensorflow 2.0 (@ tf.keras)
# Architectures

## Teacher Model

A simple CNN with every convolution layer followed by a pooling layer, ends up with a 256-unit dense layer and a softmax.

![img](/img/teacher-model.png)



## Student Model

A minimal vanilla neural network with 1 64-unit hidden layer followed by a softmax. This model is used for both student model and standalone one.

![img](/img/student-model.png)

# Result

| Model            | Test Accuracy | no. Parameters | training speed (per sample) | Epochs |
| ---------------- | ------------- | -------------- | --------------------------- | ------ |
| Teacher Model    | 70.75 %       | 1M06           | 59 μs                       | 20     |
| Student Model    | 48.61 %       | 197K           | 42 μs                       | 50     |
| Standalone Model | 39.34 %       | 197K           | 34 μs                       | 50     |
