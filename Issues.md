Following tutorial in https://pythonprogramming.net/loading-custom-data-deep-learning-python-tensorflow-keras/

Error in NeuralNetwork WIth Error was "ValueError: `validation_split` is only supported for Tensors or NumPy arrays, found following types in the input: [<class 'int'>, <class 'int'>, <class 'int'>, <class 'int'>, <class 'int'>, <class 'int'>, <class 'int'>, <class 'int'>, <class 'int'>, <class 'int'>" etc.

To resolve, imported numpy as np and added these lines below line 17 per tensorflow/tensorflow#38613 

y = []
y = np.array(y)

That worked before, but now when I do it I get this error:

ValueError: Data cardinality is ambiguous:
  x sizes: 1591
  y sizes: 0
Make sure all arrays contain the same number of samples.

When it was working, I was able to run it to create a model and then use the Predict script, but when I used the predict script it gave me a similar error to this:

Input 0 of layer conv2d_6 is incompatible with the layer: expected ndim=4, found ndim=3. Full shape received: [28, 28, 1]

Something about dimensions, though mine said ndim=2.

Something's up with  my arrays, but I haven't been able to crack it.
