
[1] **Random key**

**Description**:

Consider the operation `mapValues` after `reduceByKey`, however, for specific `key`, it has hundreds of thousands `values`, but for other `key`, it only has a few of `values`. Therefore, the total execution time is depends on the task which process the `key` that has the largest number of `values`, how to solve it ?

**SOLUTION**:
add random key.

```
from random import randint

rep_num = 100

# use
rdd_example.map(lambda x: ((x.id, randint(0, rep_num)), [x])).reduceByKey(lambda a, b: a + b, 200).mapValues(map_method)

# instead of 
rdd_example.map(lambda x: (x.id, [x])).reduceByKey(lambda a, b: a + b, 200).mapValues(map_method)
```
