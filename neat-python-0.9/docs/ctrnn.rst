Continuous-time recurrent neural network implementation
=======================================================

The default continuous-time recurrent neural network (CTRNN) implementation in neat-python
is modeled as a system of ordinary differential equations, with neuron potentials as the
dependent variables.

:math:`\tau_i \frac{d y_i}{dt} = -y_i + f_i\left(\beta_i + \sum\limits_{j \in A_i} w_{ij} y_j\right)`


Where:

* :math:`\tau_i` is the time constant of neuron :math:`i`.
* :math:`y_i` is the potential of neuron :math:`i`.
* :math:`f_i` is the activation function of neuron :math:`i`.
* :math:`\beta_i` is the bias of neuron :math:`i`.
* :math:`A_i` is the set of indices of neurons that provide input to neuron :math:`i`.
* :math:`w_{ij}` is the weight of the connection from neuron :math:`j` to neuron :math:`i`.

The time evolution of the network is computed using the forward Euler method:

:math:`y_i(t+\Delta t) = y_i(t) + \Delta t \frac{d y_i}{dt}`
