# tensorflow learning

### start
```
source activate tensorflow
python
import tensorflow as tf
```

### tf.greater
```
tf.greater(x, y, name=None)
```

return the truth value of (x > y) element-wise.

Returns: A Tensor of type bool.

### tf.Data.Dataset
```
tf.Data.Dataset.from_tensor_slices(tensor)
```

Creates a Dataset whose elements are slices of the given tensors.

*Args: tensors: A nested structure of tensors, each having the same size in the 0th dimension.

*Returns: Dataset: A Dataset.
