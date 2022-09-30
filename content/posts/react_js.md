---
title: "React_js"
date: 2022-09-27T14:03:23+05:30
draft: false
---

React is front-end framework. It is facebook's product.
JSX -  java script extend (with more syntax)


* References
  1. [React – A JavaScript library for building user interfaces](https://reactjs.org/)


* Manipulating react dom 
    * React has it's own dom than the browser's dom
    * React does the comparison of state of data in order to render the data

   ```js

   const paragrapgh = React.createElement('p',null,'hello world'); 
   // [tag] , [object of attributes] , [body]

   ReactDOM.render(paragraph, container);


##  React Life Cycle

1. render() -

      method render the each of the component

      - setState() - method on component takes a call back and executes the callback.

      If someone setState method, potentially state might have change. React checks whether state has changed or not if changed then it calls the render method that component.

2. componentDidMount() 

      called after component mounted in react dom.

3. componentWillMount()

      called when component being unmounted for react dom.

### React Component properties

1. props - 
  - Used to specify the properties of component

  ```js
    class Para extends React.Component{
      constructor(props){
        super(props);
      }
    }

  const para = React.createElement(IncrementButton,
    { style: { color: 'red' } });
  ```

2. state - 
  - The state contains data specific to this component that may change over time. 
  - The state is user-defined, and it should be a plain JavaScript object.

## Class component 

  ```js
  class IncrementButton extends React.Component{
    constructor(props) {
      super(props);
      this.state = { count: 0 };
    }

    render() {
      const button = React.createElement('button', {
        onClick: (event) => {
          this.setState(() => (this.state.count++));
        },
        style: this.props.style
      }, `Clicked ${this.state.count}`);
      return button;
    }
  }
```
Used which component needs to explicitly maintain state.

## Functional Component

```js
  const helloworld = (props) => {
    return React.createElement('p', props, 'Hello World');
  }

  const helloworldEle = React.createElement(
    helloworld, 
    { style: { color: 'red' } }
  );

  const root = ReactDOM.createRoot(mainContainer);
  root.render(helloworldEle);
```
Used when no need to maintain state of component.