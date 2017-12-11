# What and why?

Redux dispatches actions to Reducers - which handles the action and change the state. Instead of changing the old state, it creates a new one, promoting immutability.
The `store` stores the state, so the components can subscribe to certain parts of the Store, which sends automatically the data back when it changes.

## Really, what is Redux?

Redux is a tool for State management, usually used with React. One can use it with other view libraries, as well as native code.

## BUT WHY?

Sometimes, an app can get really tricky really fast, and managing the state of components - and its children - can get REALLY tricky. Redux helps to maintain things more steady and clearer.
