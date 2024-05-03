
```ts
const todoItem: TodoItem = { itemName: "the first and only todo", id: 4 };

    test("Should display passed prop", () => {
        const todoItemBlockWrapper = shallowMount(TodoItemBlock, {
            props: { todoItem: todoItem },
        });
        expect(todoItemBlockWrapper.text()).toContain("the first and only todo");
    });
```