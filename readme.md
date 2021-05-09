
## create github project with template node

## ref : https://medium.com/@masnun/typescript-with-koa-part-1-c4843f16a4ad
```bash

# create package.json
npm init -y
# install koa and packages
npm i -S koa koa-bodyparser koa-json koa-logger koa-router
npm i --save-dev @types/koa
npm i --save-dev @types/koa-router
npm i --save-dev @types/koa-logger
npm i --save-dev @types/koa-json
# create 2 directories
mkdir src dist
```

## create `src/index.ts`

```ts
import * as  Koa from "koa";
import * as Router from "koa-router";

import * as logger from "koa-logger";
import * as json from "koa-json";

const app = new Koa();
const router = new Router();

// Hello world
router.get("/", async (ctx, next) {
    ctx.body = { msg: "Hello world"};

    await next();
};)

// Middlewares()
app.use(json());
app.use(logger());

// Routes
app.use(router.Routes().use(router.allowecMethods()));

app.listen(3000, () => {
    console.log("koa started")
});
```

```bash
# install typescript
sudo npm i -g typescript
# create tsconfig.json
tsc --init
```

```js
npm i -D @types/node
```