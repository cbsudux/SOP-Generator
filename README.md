# SOP-generator

A simple LSTM based Statement of Purpose Generator for grad school. 

![Alt Text](https://github.com/cbsudux/SOP-generator/blob/master/Peek%202018-11-16%2014-57.gif)

# Prerequisites
- Pytorch 0.4
- Python 2.x /  3.x

## Generate

Generate samples from the [trained model](https://github.com/cbsudux/SOP-generator/blob/master/model.pt). 
```bash
python generate.py --data ./data/sop/ --seed 6 # play with seed to get different text
```

## Training

```bash
python main.py --cuda --epochs 500 --data data/sop/ --tied # Train a tied LSTM on SOP dataset with CUDA for 500 epochs
```

The model uses the `nn.RNN` module (and its sister modules `nn.GRU` and `nn.LSTM`)
which will automatically use the cuDNN backend if run on CUDA with cuDNN installed.

During training, if a keyboard interrupt (Ctrl-C) is received,
training is stopped and the current model is evaluated against the test dataset.

## Contributors

- [Sudharshan Chandra Babu](http://github.com/cbsudux)
- [Shishira R Maiya](https://github.com/abhyantrika)

## Credits

[pytorch/examples/tree/master/word_language_model](https://github.com/pytorch/examples/tree/master/word_language_model)
