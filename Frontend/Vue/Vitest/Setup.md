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



