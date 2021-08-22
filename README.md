**## WHAT WILL I LEARN**

- Avoid wasted rendering
- Reducing the bundle size of the app
- Loading components on demand
- Caching expensive operation results

> I will know how to troubleshoot and fix most perfomance issues in react apps

**## AUTHOR**

Hendrik Swanepoel - Software Engineer @ GoDaddy

**## BEWARE**

Premature optimization is a trap

- Almost all the time is a time-wasted
- It's hard to prevent / mitigate all the wasted renders

**## HOW RENDER WORKS**

1 - React asks for components about their latest markup;

2 - Pushes that markup back into the Browser DOM;

- THE PROBLEM: If we need to do this procedure all over again, it makes the app unusable.

3 - It maps the markups added, removed, changed and adds into the Virtual DOM.

4 - React does not take every render and reconcile with the Actual DOM.

- It's smart enought to loop and knows when there is enought changes that needs to publish to the DOM
- It's a very cheap in-memory structure.

**## TIPS**

- `React.PureComponent`: equal to the `React.memo`.
    - But `React.memo` its more flexible b/c it accepts a function to do the props comparison.
        - CLASS: `shouldComponentUpdate`
        - FUNCTIONAL: `2nd props`

```
function MyComponent(props) {
  /* renderize usando props */
}
function areEqual(prevProps, nextProps) {
  /*
  se prevProps e nextProps renderizam o mesmo resultado,
  retorne true.
  caso contrário, retorne false.
  */
}
export default React.memo(MyComponent, areEqual);
```

**## LINKS**

[https://github.com/hendrikswan/pluralsight-react-performance](https://github.com/hendrikswan/pluralsight-react-performance)

**## SCRIPTS**

- `start`: builds and runs the project @ :4000.
- `build`: builds the project.
- `test`: runs the tests of the project.