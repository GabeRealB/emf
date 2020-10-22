# Function `emf_config_get_num_namespaces`

```c
size_t emf_config_get_num_namespaces(
    const emf_config_namespace_t* group,
    emf_bool_t recursive
);
```

Returns the number of namespaces.

Returns the number of namespaces inside (and including) the supplied namespace.
The namespaces can be counted recursively by setting `recursive` to `emf_bool_true`.
The namespace `NULL` and the empty namespace refer to the global namespace.

## Undefined Behaviour

The callee expects that the caller holds a lock (See [emf_lock()](./fn.emf_lock.md)).  
Furthermore, the caller must ensure that the following preconditions hold:

```c
ASSERT(
    group == NULL ||
    emf_config_namespace_exists(group) == emf_bool_true
);
```