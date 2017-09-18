[![Enigma Pattern Inc.](https://raw.githubusercontent.com/EnigmaPatternInc/EnigmaCode/master/Enigma_github.png)](http://www.enigmapattern.com)
## EnigmaCode

## Tools we used

### AI that classifies the German language
We used a two-layered recurrent neural network (first layer: 50 LSTM neurons, second layer: simple sigmoid neuron as the output). We trained the network on 10 letters German words against 10 letters random strings. Since they are VERY different, even this simple approach proved to be successful.  
Technologies: keras (on TensorFlow)

### Enigma simulator
We wrote a small python system that mimicked the Enigma rotors and plugs. Also, since checking the output in the neural networks took too long, we filtered them out first, by checking if the output follows the frequencies of two-letters substrings in the German language. This was a quick and elegant solution to reduce the amount work for neural network to less than 1% of the initial batch.  
Technologies: pure python, one thread

### 1000 servers system

## Things that worked well


## Things we would do differently now
