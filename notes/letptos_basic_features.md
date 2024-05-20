# Leptos Basic Features

## Resource, Suspense, and spawn_local 
- They are all features related with async.
- Reasource and suspense are used to sync rendering with async request.
- spawn_local is for purely to spawn a task to run a Future.


## How to use server function as API 
- See examples for [Actix](https://github.com/leptos-rs/leptos/blob/main/examples/todo_app_sqlite/src/main.rs#L44) and [Axum](https://github.com/leptos-rs/leptos/blob/598523cd9d0d775b017cb721e41ebae9349f01e2/examples/todo_app_sqlite_axum/src/main.rs#L51).

## Only Get and Post Request are supported 
- See [Server Function Encodings](https://book.leptos.dev/server/25_server_functions.html#server-function-encodings)

## What are the usual ways to integrate server functions with Leptos 
- Create `resources` that call the server function to load data from the server.
- Read resources under `<Suspense/>` or `<Transition/>` to enable streaming SSR and fallback states while data loads.
- Create `actions` that call the server function to mutate data on server.

## Extractors
- It is useful because it provides an easy way to access request data inside server functions.
- [Axum Extractors](https://book.leptos.dev/server/26_extractors.html#axum-extractors)
  - [How to extract session data for authentication](https://github.com/leptos-rs/leptos/blob/19ea6fae6aec2a493d79cc86612622d219e6eebb/examples/session_auth_axum/src/main.rs#L24-L44)
- [axum-state](https://book.leptos.dev/server/26_extractors.html#axum-state)
- Use `provide_context` to provide shared server data.

## How to set the response
- [ResponseOptions](https://book.leptos.dev/server/27_response.html#responseoptions) is provided as context.

## Progressive enhancement and graceful degradation

- What is the differences between `<ActionForm/>` and `<Form/>` ?
  - It is just a `<form>` fires a `submit` event.
  - It is a progressive enhancement on `<Form/>`
- How to create `<ActionForm/>`? 
  - See: [4 steps to create ActionForm](https://book.leptos.dev/progressive_enhancement/action_form.html#actionform)
