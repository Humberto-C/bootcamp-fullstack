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
    
    this.handleSubmit = this.handleSubmit.bind(this);
    this.handleChangeText = this.handleChangeText.bind(this);
    this.handleChangeTextArea = this.handleChangeTextArea.bind(this);
    this.handleChangePrio = this.handleChangePrio.bind(this);

  }
  
  handleSubmit(event) {
    event.preventDefault();
    this.props.send(this.state);
  }
  
  handleChangeText(event) {
    this.setState({
      name: event.target.value
    });
  }
  
  handleChangeTextArea(event) {
    this.setState({
      wish: event.target.value
    });
  }
  
  handleChangePrio(event) {
    this.setState({
      priority: event.target.value
    });
  }

  
  render() {
    return (
      
      <form onSubmit={this.handleSubmit}>
        <label for="name">Name:
          <input 
            type="text" 
            id="name" 
            name="name" 
            value={this.state.name}
            onChange={this.handleChangeText}
          />
        </label>  
        <label>Describe your wish..
          <textarea 
            id="wish" 
            name="wish" 
            value={this.state.wish}
            onChange={this.handleChangeTextArea}
          />
        </label>
        <label for="priority">Priority of the Wish
          <select 
            name="priority" 
            id="priority" 
            value={this.state.priority}
            onChange={this.handleChangePrio}
          >
            <option value="1">1</option>
            <option value="2">2</option>
            <option value="3">3</option>
            <option value="4">4</option>
            <option value="5">5</option>
          </select>
        </label>
      </form>
    );
  }
};

  ```
  
</details>
