# No if-else statements in JSX

https://react-cn.github.io/react/tips/if-else-in-JSX.html

Because JSX is just shorthand for

```
React.createElement("div", {id:"msg"}, "Hello World!")
```

Alternatives:

1. ternary

```
class MovieCard extends Component {

  render() {
    const { users, movieFans, movieInfo } = this.props;
    return (
      <li key={movieInfo.id}>
        <h2>{movieInfo.name}</h2>
        <h3>Liked By:</h3>

        { ( movieFans && movieFans.length > 0 ) ?
            (<ul>
            {movieFans.map(userID => {
              return (
                <li key={userID}>
                  <p>{users[userID].name}</p>
                </li>
              )
            })}
            </ul>) :
            <p>None of the current users liked this movie.</p>
        }

      </li>
    );
  }
}
```

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
