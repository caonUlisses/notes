# What and why?

Redux dispatch actions to Reducers - which handles the action and change the state. Instead of changing the old state, it creates a new one, promoting immutability.
The `store` stores the state, so the components can subscribe to certain parts of the Store, which sends automatically the data back when it changes.

## Really, what is Redux?

Redux is a tool for State management, usually used with React. One can use it with other view libraries, as well as native code.