#  Week 3 - Tuesday

## Fetch Random User Data ✔️

### Description

React code to fetch from [this](https://jsonplaceholder.typicode.com/) API random users. You should display the Name, website, email and phone of a random user. Also there should be a Reset button to fetch a new user (For this you need to generate a random number from 1 to 10).

``` Example ```

![randomUserData image](/src/images/userdata.gif)

<details>
  <summary>Solution</summary>
  
  ```js
  
  import React, { useState, useEffect } from 'react';


export default function App() {
    const [users, setUsers] = useState();
    const [random, setRandom] = useState(1);


    useEffect(() => {
        getApiData();
    }, []);

    // Function to collect data
    const getApiData = async () => {
        const response = await fetch(
            "https://jsonplaceholder.typicode.com/users"
        ).then((response) => response.json());

        setUsers(response);
    };



    const handleClick = () => {
        setRandom(Math.floor(Math.random() *(11-1) + 1));
    }

    return (
        <>
            <div className="App">
                <button onClick={handleClick}>Reset</button>
                {users && users.filter(user => user.id == random).map((user) => (
                    <div className="item-container" key={user.id}>
                        <p>Name:{user.name}</p>
                        <p>Website:{user.website}</p>
                        <p>Email:{user.email}</p>
                        <p>Phone:{user.phone}</p>
                    </div>
                ))}
            </div>
        </>
    );
}

  
  ```
  
</details>

