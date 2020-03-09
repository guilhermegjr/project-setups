# Install Vue + Plugins + Create the app

1. Install the Vue CLI: `npm i -g @vue/cli`
2. Create the app: `vue create <nome da aplicação>`
3. Install the store plugins: `npm i -s logrocket logrocket-vuex` 

# Seting up the store

1. Create the root-store file: In the Store folder create a file named as `root-state.ts` and add the content bellow
``` typescript 
export default interface RootState {}
```

2. In the `index.ts` file add the following content
``` typescript 
import Vue from "vue";
import Vuex, { StoreOptions } from "vuex";
import LogRocket from "logrocket";
// @ts-ignore
import createPlugin from "logrocket-vuex";
import RootState from "./root-state";
import module1 from "./module1";
import moduleN from "./moduleN";

Vue.use(Vuex);

const logrocketPlugin = createPlugin(LogRocket);

export const store: StoreOptions<RootState> = {
  state: {},
  modules: {
    module1,
    moduleN
  },
  plugins: [logrocketPlugin]
};

export default new Vuex.Store<RootState>(store);
```
