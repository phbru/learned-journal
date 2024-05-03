With the proper setup


```ts
import { createTestingPinia } from "@pinia/testing";
import { useTodoListStore } from "@/stores/todoListStore";
import { nextTick } from "vue";

test("renders 3 TODOs", async () => {
        const wrapper = mount(TodoList, {
            global: {
                plugins: [createTestingPinia()],
            },
        });

        const store = useTodoListStore();
        store.todoItems = [
            { itemName: "manger", id: 0 },
            { itemName: "aller dormir", id: 1 },
            { itemName: "chanter des belles chansons", id: 2 },
        ];
        await nextTick();
        const items = wrapper.findAllComponents(TodoItem);
        expect(items).toHaveLength(3);
    });
```


