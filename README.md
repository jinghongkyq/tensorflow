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

```
interleave
interleave(map_func, cycle_length, block_length=1)
```

Maps `map_func` across this dataset, and interleaves the results, you can use `Dataset.interleave()` to process many input files concurrently.

The `cycle_length` and `block_length` arguments control the order in which elements are produced. `cycle_length` controls the number of input elements that are processed concurrently. If you set `cycle_lengt`h to 1, this transformation will handle one input element at a time, and will produce identical results = to `tf.data.Dataset.flat_map`. In general, this transformation will apply `map_func` to `cycle_length` input elements, open iterators on the returned Dataset objects, and cycle through them producing `block_length`  consecutive elements from each iterator, and consuming the next input element each time it reaches the end of an iterator.

```
# NOTE: The following examples use `{ ... }` to represent the
# contents of a dataset.
a = { 1, 2, 3, 4, 5 }

# NOTE: New lines indicate "block" boundaries.
a.interleave(lambda x: Dataset.from_tensors(x).repeat(6),
             cycle_length=2, block_length=4) == {
    1, 1, 1, 1,
    2, 2, 2, 2,
    1, 1,
    2, 2,
    3, 3, 3, 3,
    4, 4, 4, 4,
    3, 3,
    4, 4,
    5, 5, 5, 5,
    5, 5,
}
```

### tf.cast
```
tf.cast(x, dtype, name=None)
```

Casts a tensor to a new type.

```
x = tf.constant([1.8, 2.2], dtype=tf.float32)
tf.cast(x, tf.int32)  # [1, 2], dtype=tf.int32
```
