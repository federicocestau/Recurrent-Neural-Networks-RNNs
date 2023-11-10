# Recurrent-Neural-Networks-RNNs
Modeling and predicting sequential data requires a different approach from standard regression or classification. Luckily, a particular type of Neural Networks called Recurrent Neural Networks (RNNs) are specifically designed for that purpose.

The hidden units inside RNN have a built-in feedback loop, enabling the information to be passed back to the same node multiple times. These hidden units are commonly called recurrent units.

A recurrent unit processes information for a predefined number of timesteps, each time passing a hidden state and an input for that specific timestep through an activation function.
The hidden state of an RNN can capture historical information of the sequence up to the current time step. 
Timestep — single processing of the inputs through the recurrent unit. E.g., if you have only one timestep, then your inputs will only be processed once (equivalent to a regular hidden node). If you have seven timesteps, then your inputs will be processed seven times.

•	Inputs — while you may have only one input node, you would have to pass sequences of three numbers as your input because that is what’s required by the recurrent layer, i.e. [x0, x1, x2], …, [x_{n-2}, x_{n-1}, x_{n}].

•	Recurrent layer — in a typical feed-forward neural network, the hidden node would have two parameters: weight and bias. However, a recurrent layer has three parameters to optimize: weight for the input, weight for the hidden unit, and bias. Note that it would still be three parameters even if you had ten timesteps.

•	Training — a typical feed-forward neural network is trained using a backpropagation algorithm. Meanwhile, training an RNN uses a slightly modified version of backpropagation, which includes the unfolding in time to train the weights of the network. The algorithm is based on computing the gradient vector and is called backpropagation in time or BPTT for short.

Conceptually, BPTT works by unrolling all input timesteps. Each timestep has one input timestep, one copy of the network, and one output. Errors are then calculated and accumulated for each timestep. The network is rolled back up and the weights are updated.

