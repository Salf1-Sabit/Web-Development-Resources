## About hooks

1. Hooks can only be used in functional components.
2. They can never be used in any blok such as "if statements or loops".
3. They must stay at the top of the functional component.

## useState() hook

1. useState always returns an array with two values. Which is current-state and update function for current-state. <br/>

   ```Javascript
    const [currentState, updateFunction] = useState();
   ```

2. To control the update function we need a function which will be called to handle the change of the state.

   ```Javascript
   function App() {
    return (
        function handleChange () {
            updateFunction(currentState - 1);
        }
        <div>
            <button onclick={handleChange}> Click me </button>
        </div>
    )
   }
   ```

3. The aforementioned updating method is not correct. Because, if we do this:

   ```Javascript
    function handleChange () {
        updateFunction(currentState - 1);
        updateFunction(currentState - 1);
        // currentState will only decrement by 1
        // Because, it is changing corresponding to the current state-value.
    }
   ```

   So, the correct way to do this is:

   ```Javascript
   function handleChange () {
        updateFunction(prevState => prevState - 1);
        updateFunction(prevState => prevState - 1);
        // currentState will only decrement by 2
        // Because, it is changing corresponding to the latest state-value.
    }

   ```
