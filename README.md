# js_interview
### useRef hook : 
In React, useRef holds and returns a mutable object with a single property called .current. This object persists across re-renders of the component, and any changes to .current do not trigger re-renders.
When you call useRef(), it returns an object like this:
```
const refObject = useRef(initialValue);
```
