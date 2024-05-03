Vue offers common stup components

- RouterLinkStub


```ts
import {RouterLinkStub} from '@vue/test-utils';

const wrapper = shallowMount(SongItem, {
	global:{
		components:{
			'router-link':RouterLinkStub,
		}
	}
});
```