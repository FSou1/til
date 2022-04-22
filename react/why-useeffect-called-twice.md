# Why a React component is rendered twice?

One of the reason is: Strict Mode.

StrictMode renders components twice (on dev but not production) in order to detect any problems with your code and warn you about them (which can be quite useful).

Strict mode can’t automatically detect side effects for you, but it can help you spot them by making them a little more deterministic. This is done by intentionally double-invoking the functions like `constructor`, `render`, `useEffect`, etc.

References:
* https://reactjs.org/docs/strict-mode.html#detecting-unexpected-side-effects