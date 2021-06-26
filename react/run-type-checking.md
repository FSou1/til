# How to run type checking on the props

To run typechecking on the props for a component, you can assign the special `propTypes` property:

```javascript
import PropTypes from 'prop-types';

class Greeting extends React.Component {
  render() {
    return (
      <h1>Hello, {this.props.name}</h1>
    );
  }
}

Greeting.propTypes = {
  name: PropTypes.string
};
```

This also works with a function component:

```javascript
import PropTypes from 'prop-types';

const Greeting = (props) => {
  return (
    <h1>Hello, {props.name}</h1>
  );
}

Greeting.propTypes = {
  type: PropTypes.string.isRequired
}

export default Greeting;
```

References:
* https://reactjs.org/docs/typechecking-with-proptypes.html