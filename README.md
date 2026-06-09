# Ex04 Simple Calculator - React Project
## Date:08-06-2026
## Name : Thenamizhthan V
## Reg No : 212225240175

## AIM
To  develop a Simple Calculator using React.js with clean and responsive design, ensuring a smooth user experience across different screen sizes.

## ALGORITHM
### STEP 1
Create a React App.

### STEP 2
Open a terminal and run:
  <ul><li>npx create-react-app simple-calculator</li>
  <li>cd simple-calculator</li>
  <li>npm start</li></ul>

### STEP 3
Inside the src/ folder, create a new file Calculator.js and define the basic structure.

### STEP 4
Plan the UI: Display screen, number buttons (0-9), operators (+, -, *, /), clear (C), and equal (=).

### STEP 5
Create a new file Calculator.css in src/ and add the styling.

### STEP 6
Open src/App.js and modify it.

### STEP 7
Start the development server.
  npm start

### STEP 8
Open http://localhost:3000/ in the browser.

### STEP 9
Test the calculator by entering numbers and operations.

### STEP 10
Fix styling issues and refine content placement.

### STEP 11
Deploy the website.

### STEP 12
Upload to GitHub Pages for free hosting.

## PROGRAM
~~~
Calculator.jsx
import React, { useState } from 'react';

function Calculator() {
  const [input, setInput] = useState('');

  const handleClick = (value) => {
    if (value === '=') {
      try {
        setInput(eval(input).toString());
      } catch {
        setInput('Error');
      }
    } else if (value === 'C') {
      setInput('');
    } else {
      setInput(input + value);
    }
  };

  const buttons = ['7', '8', '9', '/', '4', '5', '6', '*',
                   '1', '2', '3', '-', '0', '.', '=', '+', 'C'];

  return (
    <div className="calculator">
      <h3>Simple Calculator</h3>
      <input value={input} readOnly className="display" />
      <div className="button-grid">
        {buttons.map((btn) => (
          <button key={btn} onClick={() => handleClick(btn)}>{btn}</button>
        ))}
      </div>
    </div>
  );
}

export default Calculator;
Calculator.css
.calculator {
  width: 320px;            
  background-color:black; 
  border-radius: 20px;      
  padding: 20px;
  margin: 50px auto;        
  box-shadow: 0 10px 30px rgba(197, 231, 25, 0.6);
  text-align: center;
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  box-sizing: border-box;   /* include padding in width */
}

/* Display screen fixed inside calculator */
.display {
  width: 100%;             /* full width of calculator */
  padding: 15px;
  font-size: 2rem;
  text-align: right;
  margin-bottom: 20px;
  background-color: #3ae8e8; /* black background */
  color: #ffffff;           
  border: none;
  border-radius: 12px;
  box-shadow: inset 0 -3px 6px rgba(0,0,0,0.5);
  box-sizing: border-box;   /* include padding in width */
}

/* Buttons grid */
.button-grid {
  display: grid;
  grid-template-columns: repeat(4, 1fr);
  gap: 15px; /* uniform spacing */
}

/* General button style */
button {
  padding: 20px;
  font-size: 1.5rem;
  border: none;
  border-radius: 12px;
  cursor: pointer;
  color: white;
  width: 100%;
  transition: transform 0.1s, background-color 0.2s;
  box-shadow: 0 5px 10px rgba(0,0,0,0.4);
}

/* Hover effect */
button:hover {
  transform: scale(1.05);
}

/* Number buttons */
button:nth-child(-n+16):not(:nth-child(4n)) {
  background-color: #3b82f6; /* vibrant blue */
}

button:nth-child(-n+16):not(:nth-child(4n)):hover {
  background-color: #2563eb;
}

/* Operator buttons (+, -, *, /) */
button:nth-child(4n) {
  background-color: #f97316; /* bright orange */
}

button:nth-child(4n):hover {
  background-color: #ea580c;
}

/* Clear button (C) */
button:nth-child(17) {
  background-color: #ef4444; /* red */
}

button:nth-child(17):hover {
  background-color: #dc2626;
}

/* Equals button (=) */
button:nth-child(18) {
  background-color: #22c55e; /* green */
}

button:nth-child(18):hover {
  background-color: #16a34a;
}

/* Responsive tweaks */
@media (max-width: 350px) {
  .calculator {
    width: 90%;
    padding: 15px;
  }
  .display {
    padding: 15px;
    font-size: 1.5rem;
  }
  button {
    padding: 15px;
    font-size: 1.2rem;
  }
}
App.jsx
import React from 'react';
import Calculator from './Calculator';
import './Calculator.css';

function App() {
  return (
    <div className="App">
      <Calculator />
    </div>
  );
}

export default App;
~~~
## OUTPUT
<img width="428" height="826" alt="image" src="https://github.com/user-attachments/assets/6d8ac1e1-51ff-4433-92ab-1e1e21ce035c" />


## RESULT
The program for developing a simple calculator in React.js is executed successfully.
