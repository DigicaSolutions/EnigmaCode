[![Enigma Pattern Inc.](https://raw.githubusercontent.com/EnigmaPatternInc/EnigmaCode/master/Enigma_github.png)](http://www.enigmapattern.com)
## EnigmaCode

This is the technical specification of our Breaking the Enigma Code project, you can read more about it here: 
[https://www.linkedin.com/pulse/how-we-cracked-enigma-code-using-artificial-lukasz-kuncewicz/](https://www.linkedin.com/pulse/how-we-cracked-enigma-code-using-artificial-lukasz-kuncewicz/).

## Tools we used

### AI that classifies the German language
We used a two-layered recurrent neural network (first layer: 50 LSTM neurons, second layer: simple sigmoid neuron as the output). We trained the network on 10 letters German words against 10 letters random strings. Since they are VERY different, even this simple approach proved successful.  
Technologies: keras (on TensorFlow)

### Enigma simulator
We wrote a small python system that mimicked the Enigma rotors and plugs. Also, since checking the output in the neural networks took too long, we filtered them by checking if the output follows the frequencies of two-letters substrings in the German language. This was a quick and elegant solution to reduce the amount work for neural network to less than 1% of the initial batch.  
Technologies: pure python, one thread only

### 1000 servers system
We used DigitalOcean and their API to create a 1000 of their smaller droplets (virtual servers). They were connected to RabbitMQ (installed on a slightly bigger droplet) resposible for distributing the combinations to check and for gathering the results. We stored them for the final checkout in SQLite.  
Technologies: DigitalOcean API, RabbitMQ, SQLite.

## Things we would do differently now
* writting the Enigma simulator in C++ - this would speed the module a few times (estimation)
* adding an AI that would try to guess the plugs - the same way Turing did - this would allow us to take more plugs into consideration, growing the number of passwords' combinations
