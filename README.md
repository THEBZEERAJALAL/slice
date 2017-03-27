# slice
###

`tf.slice(
    input_,
    begin,
    size,
    name=None
)`



Extracts a slice of size `size`  from a tensor `input` starting at the location specified by `begin`. Begin is zero-based, size is one-based. If size[i] is -1, all remaining elements in dimension i are included in the slice. 


For Example:
````
input = [
        [[0, 1, 3], [4, 5, 6]],
        [[7, 8, 9], [11, 12, 13]],
        [[14, 15, 16], [17, 18, 19]]
        ]

a = tf.slice(input, [0, 0, 0], [1, -1, 1])
b = tf.slice(input, [1, 0, 0], [1, 1, 3])
c = tf.slice(input, [2, 0, 0], [1, 2, 3])
d = tf.slice(input, [0, 0, 0], [3, 2, 3])

init = tf.global_variables_initializer()
sess = tf.Session()
sess.run(init)

print(sess.run(a))
print("********************")
print(sess.run(b))
print("********************")
print(sess.run(c))
print("********************")
print(sess.run(d))

````
Output:

````
[[[0]
  [4]]]
********************
[[[7 8 9]]]
********************
[[[14 15 16]
  [17 18 19]]]
********************
[[[ 0  1  3]
  [ 4  5  6]]

 [[ 7  8  9]
  [11 12 13]]

 [[14 15 16]
  [17 18 19]]]
  ````


