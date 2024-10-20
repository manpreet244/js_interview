# js_interview
### useRef hook : 
In React, useRef holds and returns a mutable object with a single property called .current. This object persists across re-renders of the component, **and any changes to .current do not trigger re-renders** .
When you call useRef(), it returns an object like this:
```
const refObject = useRef(initialValue);
```
This refObject has the following structure:
```
{
  current: initialValue
}
```
### The current Property:
  1) The main property useRef returns is .current. You can read or modify its value, and this value will persist between renders.   
  2) current starts with the initialValue you provide to useRef(). If no value is provided, it's initialized as undefined.
### No Re-Renders on Update:
  1) Unlike useState, changing refObject.current does not cause the component to re-render.
  2) This makes it ideal for storing values that need to persist across renders but don’t affect the UI directly (e.g., DOM elements, timers, previous state values).
  ### Accessing DOM elements:
  1) You can attach useRef to a DOM element using the ref attribute, which gives you direct access to the element.
```
import React, { useRef, useEffect } from 'react';

function ExampleComponent() {
  const inputRef = useRef(null);

  useEffect(() => {
    // Focus the input field when the component mounts
    inputRef.current.focus();
  }, []);

  return (
    <div>
      <input ref={inputRef} placeholder="Focus on mount" />
    </div>
  );
}

export default ExampleComponent;
```
