# Usage-of-Initializers-in-Keras
Usage of Initializers in Keras

Initializations define the way to set the initial random weights of Keras layers.
The keyword arguments used for passing initializers to layers will depend on the layer. Usually it is simply kernel_initializer and bias_initializer:

model.add(Dense(64,
                kernel_initializer='random_uniform',
                bias_initializer='zeros'))
             
The following built-in initializers are available as part of the keras.initializers module:
# 1. keras.initializers.Initializer()
Initializer base class: all initializers inherit from this class.

# 2. keras.initializers.Zeros()
Initializer that generates tensors initialized to 0.

# 3. keras.initializers.Ones()
Initializer that generates tensors initialized to 1.

# 4. keras.initializers.Constant(value=0)
Initializer that generates tensors initialized to a constant value.

# 5. Random Normal Initializer
# keras.initializers.RandomNormal(mean=0.0, stddev=0.05, seed=None)
Initializer that generates tensors with a normal distribution.
# Arguments
mean: a python scalar or a scalar tensor. Mean of the random values to generate.
stddev: a python scalar or a scalar tensor. Standard deviation of the random values to generate.
seed: A Python integer. Used to seed the random generator.

# 6.Truncated Normal Initializer
# keras.initializers.TruncatedNormal(mean=0.0, stddev=0.05, seed=None)
Initializer that generates a truncated normal distribution.
These values are similar to values from a RandomNormal except that values more than two standard deviations from the mean are discarded and redrawn. This is the recommended initializer for neural network weights and filters.

# 7.Xavier Normal Initializer / Glorot Normal Initializer
# keras.initializers.glorot_normal(seed=None)
It draws samples from a truncated normal distribution centered on 0 with stddev = sqrt(2 / (fan_in + fan_out)) where,
fan_in is the number of input units in the weight tensor
fan_out is the number of output units in the weight tensor
# Arguments
seed: A Python integer. Used to seed the random generator
It returns an initializer.

