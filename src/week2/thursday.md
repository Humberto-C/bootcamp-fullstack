#  Week 2 - Thursday

## Santa wish list form in ReactJS ✔️

Santa wants to simplify his life and offer children the possiblity to enter their wishlist via an online form.

The form should be a React component and should contain:

- an input field for the child's name (with id 'name')
- a text area to describe the wish (id: 'wish')
- a drop-down indicating the priority of the wish, from 1 to 5 - default is 1 (id: 'priority')
- the keys in the state to store the corresponding values should be named the same as the element's id
- an onSubmit action calling the function handleSubmit
- a function called handleSubmit, which
  - calls send (a function that is already provided as part of the injected properties props)
  - passes the current state as a parameter to send
  - calls event.preventDefault
- it should be a controlled component (i.e. using onChange to bind input to the component's state)


<details>
  <summary>Solution</summary>
  
  ```js
    
  const React = require("react");

class WishlistForm extends React.Component {
  constructor(props) {
    super(props);
    this.state = {
      name: "",
      wish: "",
      priority: 1,
    }
  }
  
  handleSubmit() {
    
    onSubmit.preventDefault;
    this.props.send(this.state);

  }
  

  
  render() {
    return (
      
      <form onSubmit={() => {handleSubmit()}}>
        <label for="name" >Name</label>
        <input type="text" id="name" name="name" placeholder="Enter your name..."/>
        <label for="wish">Describe your wish</label>
        <textarea id="wish" name="wish"/>
        <label for="priority">Priority of the Wish</label>
        <select name="priority" id="priority">
          <option value="1">1</option>
          <option value="2">2</option>
          <option value="3">3</option>
          <option value="4">4</option>
          <option value="5">5</option>
        </select>
      </form>
    );
  }
};

  ```
  
</details>
