# No if-else statements in JSX

https://react-cn.github.io/react/tips/if-else-in-JSX.html
Because JSX is just shorthand for
React.createElement("div", {id:"msg"}, "Hello World!")

Alternatives:

1. ternary
2. Set the value outside of the JSX (above the return statement) (above the render statement?)

```
var logInOutButton;
if (loggedIn) {
    logInOutButton = <LogoutButton />
} else {
    logInOutButton = <LoginButton />
}

return (
    <nav>
        <Home />
        {logInOutButton}
    </nav>
);
```

3. define immediately-invoked function expressions inside your JSX:
