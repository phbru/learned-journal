## vitest.config.ts
```ts
import { fileURLToPath } from "node:url";
import { mergeConfig, defineConfig, configDefaults } from "vitest/config";
import viteConfig from "./vite.config";

export default mergeConfig(
    viteConfig,
    defineConfig({
        test: {
            globals: true,
            environment: "jsdom",
            exclude: [...configDefaults.exclude, "e2e/**"],
            root: fileURLToPath(new URL("./", import.meta.url)),
        },
    }),
);

```


Pour vuetify: 
```ts
import { fileURLToPath } from 'node:url';
import { mergeConfig, defineConfig, configDefaults } from 'vitest/config';
import viteConfig from './vite.config';

export default mergeConfig(
    viteConfig,
    defineConfig({
        test: {
            globals: true,
            environment: 'jsdom',
            exclude: [...configDefaults.exclude, 'e2e/**'],
            root: fileURLToPath(new URL('./', import.meta.url)),

            server: {
                deps: {
                    inline: ['vuetify']
                }
            }
        }
    })
```

... plein d'affaire...

npm i -D @pinia/testing



Permet de ne pas avoir à importer les mots clés de vite (et aussi de faire le trick de pinia...)
ts.config : 
```
 "compilerOptions": {
        "types": ["vitest/globals"], <==
        "module": "NodeNext"
    }
}
```

vitest.config.ts
``` 
export default mergeConfig(
    viteConfig,
    defineConfig({
        test: {
            globals: true, <==
            environment: "jsdom",
            exclude: [...configDefaults.exclude, "e2e/**"],
            root: fileURLToPath(new URL("./", import.meta.url)),
        },
    }),
);
```



