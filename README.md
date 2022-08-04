# create-svelte

Everything you need to build a Svelte project, powered by [`create-svelte`](https://github.com/sveltejs/kit/tree/master/packages/create-svelte).

## Creating a project

If you're seeing this, you've probably already done this step. Congrats!

```bash
# create a new project in the current directory
npm init svelte

# create a new project in frontend
npm init svelte frontend
```

## Developing

Once you've created a project and installed dependencies with `npm install` (or `pnpm install` or `yarn`), start a development server:

```bash
npm run dev

# or start the server and open the app in a new browser tab
npm run dev -- --open
```

## Building

To create a production version of your app:

```bash
npm run build
```

You can preview the production build with `npm run preview`.

> To deploy your app, you may need to install an [adapter](https://kit.svelte.dev/docs/adapters) for your target environment.

# Student is a project for creating tests and quizes for students

Libs to review:
- github.com/markbates/goth -> https://www.loginradius.com/blog/engineering/google-authentication-with-golang-and-goth/

To create a quick MVP Steps:
- Create your database schema on: https://dbdiagram.io
- Migrate using ` ` ...
- Generate models with sql boiler
- Generate graphql schema
- Add data validations (possible to do it in graphql schema)
- Do some pluming
- Add logic validations and business logic
- (frontend steps are a bit unclear at this point)

**Should create a template for specific stacks like: [svelte-graphql-go] or [react-swagger-go] in the format [<frontend>-<protocol>-<backend>-<db>[<frameworks>...]]


Authentication:

```go
session, err := store.Get(r, "session-name")
if err != nil {
http.Error(w, err.Error(), 500)
return
}

session.Options.Path = "/"
session.Values["user"] = user

err := session.Save(r, w)
if err != nil {
http.Error(w, err.Error(), 500)
return
}

http.Redirect(w, r, "/", 301)
```
