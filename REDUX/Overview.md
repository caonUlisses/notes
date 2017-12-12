# What and why?

Redux dispatches actions to Reducers - which handles the action and change the state. Instead of changing the old state, it creates a new one, promoting immutability.
The `store` stores the state, so the components can subscribe to certain parts of the Store, which sends automatically the data back when it changes.

## Really, what is Redux?

Redux is a tool for State management, usually used with React. One can use it with other view libraries, as well as native code.

## BUT WHY?

Sometimes, an app can get really tricky really fast, and managing the state of components - and its children - can get REALLY tricky. Redux helps to maintain things more steady and clearer.

## Gimme a brief explanation, please.

Of course, if we were to summarize Redux, it would be like:

> Redux is an implementation of flux, it consists of a way to dispatch actions and data through the application. It manipulates the state and handles the store (which is read only). It claims that every store manipulation has to be through a pure function.


