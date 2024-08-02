## Linked List Library

### Overview
This library provides basic operations for a singly linked list in C. It includes functions for creating, manipulating, and destroying linked lists.

### Usage
#### Include
```c
#include "linked_list.h"
```
#### Data Structure
The library uses a `node_t` structure to represent nodes in the linked list:
```c
typedef struct node {
    void *data;
    struct node *next;
} node_t;
```
#### Functions
* **`node_t *init_list(void)`**: Initializes an empty linked list and returns a pointer to the head.
* **`size_t count_list(node_t *head)`**: Counts the number of nodes in the linked list.
* **`void print_list(node_t *head, void (*f)(node_t *))`**: Prints the contents of the linked list using the provided function `f` to print each node.
* **`int insert_to_head(node_t **head, void *data)`**: Inserts a new node at the head of the linked list. Returns 0 on success, -1 on failure.
* **`int insert_to_tail(node_t **head, void *data)`**: Inserts a new node at the tail of the linked list. Returns 0 on success, -1 on failure.
* **`node_t *pop_head(node_t **head)`**: Removes and returns the head node of the linked list. Returns NULL if the list is empty.
* **`node_t *break_tail(node_t **head)`**: Removes and returns the tail node of the linked list. Returns NULL if the list is empty.
* **`node_t *delete_by_position(node_t **head, size_t position)`**: Deletes the node at the specified position and returns it. Returns NULL if the position is invalid.
* **`void destroy_list(node_t **head)`**: Frees the memory allocated for all nodes in the linked list.

### Example
```c
#include <stdio.h>
#include "linked_list.h"

void print_int(node_t *node) {
    printf("%d ", *(int*)node->data);
}

int main() {
    node_t *head = init_list();

    int a = 10, b = 20, c = 30;
    insert_to_head(&head, &a);
    insert_to_tail(&head, &b);
    insert_to_head(&head, &c);

    print_list(head, print_int);
    printf("\n");

    pop_head(&head);
    print_list(head, print_int);
    printf("\n");

    destroy_list(&head);
    return 0;
}
```

### Notes
* The `data` field in `node_t` is a generic void pointer. You'll need to cast it appropriately when accessing the data.
* The `destroy_list` function assumes that the data stored in each node is dynamically allocated. If this is not the case, you'll need to modify the function accordingly.
* The library does not implement error handling for invalid memory accesses. It's essential to handle potential errors in your application.

### Future Improvements
* Implement `delete_by_data` function.
* Add support for doubly linked lists.
* Implement iterator functionality.
* Improve error handling and robustness.
