#### Similar to Binary Tree

* Preorder
* Postorder
* Level Order

#### Recursion Solution of N-ary Tree

1. "Top-down" Solution

> "Top-down" means that in each recursion level, we will visit the node first to come up with some values, and pass these values to its children when calling the function recursively.

A typical "top-down" recursion function `top_down(root, params)` works like this:

```
1. return specific value for null node
2. update the answer if needed                              // answer <-- params
3. for each child node root.children[k]:
4.      ans[k] = top_down(root.children[k], new_params[k])  // new_params <-- root.val, params
5. return the answer if needed                              // answer <-- all ans[k]
```

2. "Bottom-up" Solution

> "Bottom-up" means that in each recursion level, we will firstly call the functions recursively for all the children nodes and then come up with the answer according to the return values and the value of the root node itself.

A typical "bottom-up" recursion function `bottom_up(root)` works like this:

```
1. return specific value for null node
2. for each child node root.children[k]:
3.      ans[k] = bottom_up(root.children[k])    // call function recursively for all children
4. return answer                                // answer <- root.val, all ans[k]
```