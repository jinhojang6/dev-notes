## React Input

<br/>

## Input component sample
```
import React, { useState, useRef } from 'react';

function Form() {
  const [input, setInput] = useState({
    name: '',
    username: ''
  });
  const nameInput = useRef();

  const { name, username } = input;
  
  const handleChange = e => {
    const { name, value } = e.target;
    setInputs({
      ...input,
      [name]: value
    });
  };

  const onReset = () => {
    setInput({
      name: '',
      username: ''
    });
    nameInput.current.focus();
  };

  return (
    <div>
      <input
        name="name"
        placeholder="Name"
        onChange={handleChange}
        value={name}
        ref={nameInput} // Focus this name input when resetting the form
      />
      <input
        name="username"
        placeholder="Username"
        onChange={handleChange}
        value={username}
      />
      <button onClick={onReset}>Reset</button>
      <div>
        <b>Value: </b>
        {name} ({nickname})
      </div>
    </div>
  );
}

export default Form;
```
