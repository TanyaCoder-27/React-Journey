

## ReactJS Cheat Sheet

### Basics
- **JSX**: JavaScript XML, a syntax extension that allows you to write HTML-like code inside JavaScript.
- **Components**: Building blocks of a React application, can be functional or class-based.
- **Props**: Short for properties, used to pass data from parent to child components.
- **State**: An object that represents the dynamic data of a component, can change over time.

### Component Types
- **Functional Component**: 
```javascript
function Welcome(props) {
  return <h1>Hello, {props.name}</h1>;
}
```
- **Class Component**:
```javascript
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
```

### Lifecycle Methods (Class Components)
- **componentDidMount()**: Called after the component is added to the DOM.
- **componentDidUpdate()**: Called after the component is updated.
- **componentWillUnmount()**: Called right before the component is removed from the DOM.

### Hooks (Functional Components)
- **useState()**: Allows you to add state to functional components.
```javascript
const [count, setCount] = useState(0);
```
- **useEffect()**: Allows you to perform side effects in functional components.
```javascript
useEffect(() => {
  // Code to run on component mount and update
}, [dependencies]);
```

### Handling Events
- **Event Handling**: Define event handlers like `onClick`, `onChange`, etc.
```javascript
<button onClick={handleClick}>Click me</button>
```
- **Passing Arguments**:
```javascript
<button onClick={() => handleClick(id)}>Click me</button>
```

### Conditional Rendering
- **Using if-else**:
```javascript
if (isLoggedIn) {
  return <LogoutButton />;
} else {
  return <LoginButton />;
}
```
- **Using ternary operator**:
```javascript
{isLoggedIn ? <LogoutButton /> : <LoginButton />}
```

### Lists and Keys
- **Rendering Lists**:
```javascript
const listItems = numbers.map((number) =>
  <li key={number.toString()}>{number}</li>
);
```

### Forms
- **Controlled Components**:
```javascript
class NameForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {value: ''};
  }

  handleChange = (event) => {
    this.setState({value: event.target.value});
  }

  handleSubmit = (event) => {
    alert('A name was submitted: ' + this.state.value);
    event.preventDefault();
  }

  render() {
    return (
      <form onSubmit={this.handleSubmit}>
        <label>
          Name:
          <input type="text" value={this.state.value} onChange={this.handleChange} />
        </label>
        <button type="submit">Submit</button>
      </form>
    );
  }
}
```

### Miscellaneous
- **Fragments**: A way to return multiple elements without adding extra nodes to the DOM.
```javascript
<React.Fragment>
  <ChildA />
  <ChildB />
</React.Fragment>
```
- **Higher-Order Components (HOCs)**: A function that takes a component and returns a new component.
```javascript
function withLogging(WrappedComponent) {
  return class extends React.Component {
    render() {
      return <WrappedComponent {...this.props} />;
    }
  }
}
```
### Create-React-App
- **Installation**:
```bash
npx create-react-app my-app
cd my-app
npm start
```

This covers the core concepts of ReactJS.
