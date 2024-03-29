# React useEffect

Before explaining what useEffect does I should explain the other two counterparts. We have rendering which is when the jsx on the screen needs to change you'll rerender the screen to change the props or transform them in anyway. Code must always be pure (meaning results never change when running the function x amount of times).

The other counterpart is Event handlers which are triggered and will generally change state. So when state wants to change it will have to be triggered by an event.

What if you want to change state, but you don't trigger anything and it's just trying to render code. This is where useEffects come into play. You use useEffect to change the state while not using a trigger to activate it. The best example is a `chatroom` where you want the chat to connect to the server when the chatroom is visible on the screen. Connecting to the server isn't a pure calculation (which is what rendering does) so you can't use render, and there's not really a trigger to be able to use an event to trigger the connection to the server.

Effects let you specify side effects that are caused by rendering, rather than a particular event.

Example:

```
useEffect(
  () => {
    // execute side effect
    return () => {
      // cleanup function on unmounting or re-rerunning the effect
    }
  },
  // optional dependency array
  [/* 0 or more entried */]
)
```

## Summary

The main use for `useEffect` is to be able to sync React components with external systems like _serves, APIs, or browser DOMs_. Meaning you want to make sure you really need it before using it. You don't want to use them willy nilly as having unnecessary `useEffect` hooks are prone to more errors and unnecessary performance issues.
