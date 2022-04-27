#  Week 3 - Monday

##  Build Search filter in React ✔️

### Description 

React code to build a simple search filter functionality to display a filtered list based on the search query entered by the user.

``` Example ```

![filter](/src/images/searchfilter.gif)

<details>
  <summary>Solution</summary>
  
  ```js

import React, { useEffect, useState } from 'react';


const SearchFilter = () => {

    const [textInput, setTextInput] = useState('');
    //const [arrOut, setArrOut] = useState([]);

    const brandsData = "Apple, Google, Microsoft, Amazon, Facebook, Coca-Cola, Samsung, " +
        "Disney, Toyota, McDonald's, AT&T, Intel, Nike, CISCO, General Electric, Mercedes-Benz, " +
        "Oracle, Verizon, IBM, BMW, SAP, Marlboro, Budweiser, VISA"

    const brands = brandsData.split(',');


    const handleChange = (event) => {
        setTextInput(event.target.value);
    }

    const searchedList = brands
        .filter((brand) => brand.toLowerCase().includes(textInput.toLowerCase()))
        .map((brand) => <li key={brand + Math.random() * 100}>{brand}</li>);


    return (
        <>
            <input
                type='text'
                name='searchbar'
                placeholder='Search'
                onChange={handleChange}
            ></input>
            <div>
                <ul>{searchedList.length ? searchedList : 'Not found...'}</ul>
            </div>
        </>

    )
}

export default SearchFilter;

```
  
</details>
