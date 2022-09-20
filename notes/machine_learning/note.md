### Tutorial

[PyTorch tutorial](https://sanghyu.tistory.com/88?category=1120072)

### Model 관련

[How to apply ResNet when input size is different](https://velog.io/@uvictoli/%EB%AA%A8%EB%91%90%EB%A5%BC-%EC%9C%84%ED%95%9C-%EB%94%A5%EB%9F%AC%EB%8B%9D2-CNN-6-ResNet)

[ResNet code review](https://bluehorn07.github.io/2020/12/07/resNet-code.html)

### RuntimeError: CUDA out of memory.

<https://aigong.tistory.com/137>

<https://stackoverflow.com/questions/54374935/how-to-fix-this-strange-error-runtimeerror-cuda-error-out-of-memory>

<https://pytorch.org/docs/stable/notes/faq.html>

<https://mollymollang.tistory.com/29>

<https://velog.io/@xdfc1745/Cuda-Out-Of-Memory>

<https://beausty23.tistory.com/145>

<https://mirae-kim.tistory.com/52>

<https://discuss.pytorch.kr/t/cuda-out-of-memory-%EC%98%A4%EB%A5%98-%ED%95%B4%EA%B2%B0/55>

[Model evaluation categories](https://stats.stackexchange.com/questions/187335/validation-error-less-than-training-error)

### Predicting negative values

<https://www.reddit.com/r/learnmachinelearning/comments/eisotm/what_is_the_best_way_to_deal_with_negative/>

<https://discuss.pytorch.org/t/how-can-my-net-produce-negative-outputs-when-i-use-relu/19483/8>

<https://stackoverflow.com/questions/69361678/the-output-of-my-neural-network-is-negative-even-if-i-am-using-relu-on-every-lay>

<https://www.researchgate.net/post/How-can-I-avoid-negative-values-in-the-output-of-a-feedforward-net>

#### target variable scaling (normalization)

<https://machinelearningmastery.com/how-to-transform-target-variables-for-regression-with-scikit-learn/>

<https://datascience.stackexchange.com/questions/35603/it-is-helpful-to-normalize-target-variables-for-a-regression-neural-network>

<https://stats.stackexchange.com/questions/111467/is-it-necessary-to-scale-the-target-value-in-addition-to-scaling-features-for-re>

<https://stackoverflow.com/questions/45449922/should-you-normalize-outputs-of-a-neural-network-for-regression-tasks>

### Loss decreasing not properly

[Why is my validation loss lower than my training loss?](https://stackoverflow.com/questions/60126101/why-is-my-validation-loss-lower-than-my-training-loss)

[Validation Loss is not decreasing - Regression model](https://datascience.stackexchange.com/questions/67549/validation-loss-is-not-decreasing-regression-model)

[What to do if training loss decreases but validation loss does not decrease?](https://datascience.stackexchange.com/questions/37815/what-to-do-if-training-loss-decreases-but-validation-loss-does-not-decrease)

[Validation loss increases while validation accuracy is still improving](https://github.com/keras-team/keras/issues/3755)

[**What is a Learnig Curve in** Machine Learning?](https://www.baeldung.com/cs/learning-curve-ml)

### Using Multiple GPUs

[Run Pytorch on Multiple GPUs](https://discuss.pytorch.org/t/run-pytorch-on-multiple-gpus/20932/71)

### questions 

1. [How does "K-fold cross validation" help in improving the accuracy of test and train data?](https://www.quora.com/How-does-K-fold-cross-validation-help-in-improving-the-accuracy-of-test-and-train-data)

> K fold validation does not help in improving accuracy of test and train data. What it does is help us in finding stable models and that we do not overfit the model on a training data set.

2. [manual split not random](https://stackoverflow.com/questions/28619979/accuracy-increases-using-cross-validation-and-decreases-without)

3. [ensemble?](https://medium.com/@nutanbhogendrasharma/how-to-create-a-bagging-ensemble-of-deep-learning-models-18316faa9280)

```python
def ensemblePredictions(members, testX):
    
    # make predictions
    yhats = [model.predict(testX) for model in members]
    
    yhats = np.array(yhats)
   
    # sum across ensemble members
    summed = np.sum(yhats, axis=0)
    
    # argmax across classes
    result = np.argmax(summed, axis=1)
    
    # return the result
    return result
```

4. [Can dropout increase training data performance?](https://stackoverflow.com/questions/59044351/can-dropout-increases-training-data-performance?answertab=trending#tab-top)

4-1. [Does a dropout increase accuracy](https://www.quora.com/Does-a-dropout-increase-accuracy)

5. [What is pre training a neural network?](https://stats.stackexchange.com/questions/193082/what-is-pre-training-a-neural-network)

```
1. You have machine learning model m.
2. Pre-training: You have a dataset A on which you train m.
3. You have a dataset B. Before you start training the model, you initialize some of the parameters of m with the model which is trained on A.
4. Fine-tuning: You train m on B.
```

### Torch seed 값 고정

[여기서 참고](https://velog.io/@jaeha0725/torch-seed-%EA%B0%92-%EA%B3%A0%EC%A0%95)

[파이토치 모델 결과 재구성하기 (Pytorch Reproduction Experiement)](https://tootouch.github.io/experiment/reproduction_pytorch/)

```python
import torch
import random
import torch.backends.cudnn as cudnn

torch.manual_seed(0)
torch.cuda.manual_seed(0)
torch.cuda.manual_seed_all(0)
np.random.seed(0)
cudnn.benchmark = False
cudnn.deterministic = True
random.seed(0)
```

### Data Augmentation

> TorchIO

[PyTorch-Lightning](https://colab.research.google.com/github/fepegar/torchio-notebooks/blob/main/notebooks/TorchIO_MONAI_PyTorch_Lightning.ipynb#scrollTo=YyVSAc7WnyUj)

[TorchIO를 이용한 3D Segmentation](https://blog.promedius.ai/torchioreul-iyonghan-3d-segmentation/)

cf. [우리가 PyTorch Lightning을 써야 하는 이유](https://baeseongsu.github.io/posts/pytorch-lightning-introduction/)<br>

#### Error solution

[SubjectsDataset](https://torchio.readthedocs.io/data/dataset.html)<br>
[Image](https://torchio.readthedocs.io/data/image.html)

```
tensor – If path is not given, tensor must be a 4D torch.Tensor or NumPy array with dimensions .
```

[`prepare_data_per_node`=True](https://pytorch-lightning.readthedocs.io/en/stable/extensions/datamodules.html#why-do-i-need-a-datamodule)

[How to structure torchio.Subject for regression?](https://github.com/fepegar/torchio/issues/297)


