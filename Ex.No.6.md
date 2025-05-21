# Ex06 BMI Calculator
## Date:06-06-2025

## AIM
To create a BMI calculator using React Router 

## ALGORITHM
### STEP 1 State Initialization
Manage the current page (Home or Calculator) using React Router.

### STEP 2 User Input
Accept weight and height inputs from the user.

### STEP 3 BMI Calculation
Calculate the BMI based on user input.

### STEP 4 Categorization
Classify the BMI result into categories (Underweight, Normal weight, Overweight, Obesity).

### STEP 5 Navigation
Navigate between pages using React Router.

## PROGRAM
# BmiCalculator.jsx
```jsx

import React, { useState } from 'react';
import './BmiCalculator.css';

const BmiCalculator = () => {
  const [height, setHeight] = useState('');
  const [weight, setWeight] = useState('');
  const [bmi, setBmi] = useState(null);
  const [status, setStatus] = useState('');

  const calculateBMI = () => {
    if (!height || !weight) {
      alert('Please enter both height and weight.');
      return;
    }

    const heightInMeters = height / 100;
    const bmiValue = (weight / (heightInMeters * heightInMeters)).toFixed(2);
    setBmi(bmiValue);

    let bmiStatus = '';
    if (bmiValue < 18.5) {
      bmiStatus = 'Underweight';
    } else if (bmiValue >= 18.5 && bmiValue < 24.9) {
      bmiStatus = 'Normal weight';
    } else if (bmiValue >= 25 && bmiValue < 29.9) {
      bmiStatus = 'Overweight';
    } else {
      bmiStatus = 'Obesity';
    }
    setStatus(bmiStatus);
  };

  return (
    <div className="bmi-container">
      <h2>BMI Calculator</h2>
      <input
        type="number"
        value={height}
        onChange={(e) => setHeight(e.target.value)}
        placeholder="Height (cm)"
        className="bmi-input"
      />
      <input
        type="number"
        value={weight}
        onChange={(e) => setWeight(e.target.value)}
        placeholder="Weight (kg)"
        className="bmi-input"
      />
      <button onClick={calculateBMI} className="bmi-button">
        Calculate
      </button>
      {bmi && (
        <div className="bmi-result">
          <p>Your BMI: {bmi}</p>
          <p>Status: {status}</p>
        </div>
      )}
    </div>
  );
};

export default BmiCalculator;


```
# BmiCalculator.css
```css

/* BmiCalculator.css */

body {
  font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
  background: linear-gradient(135deg, #f5f7fa, #c3cfe2);
  margin: 0;
  padding: 0;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}

.bmi-container {
  background-color: #ffffff;
  padding: 2rem;
  border-radius: 12px;
  box-shadow: 0 8px 16px rgba(0, 0, 0, 0.1);
  width: 90%;
  max-width: 400px;
  text-align: center;
}

.bmi-container h2 {
  margin-bottom: 1.5rem;
  color: #333333;
}

.bmi-input {
  width: 100%;
  padding: 0.75rem;
  margin-bottom: 1rem;
  border: 1px solid #cccccc;
  border-radius: 8px;
  font-size: 1rem;
  transition: border-color 0.3s;
}

.bmi-input:focus {
  border-color: #007BFF;
  outline: none;
}

.bmi-button {
  width: 100%;
  padding: 0.75rem;
  background-color: #007BFF;
  color: #ffffff;
  border: none;
  border-radius: 8px;
  font-size: 1rem;
  cursor: pointer;
  transition: background-color 0.3s;
}

.bmi-button:hover {
  background-color: #0056b3;
}

.bmi-result {
  margin-top: 1.5rem;
  font-size: 1.2rem;
  color: #333333;
}


```
# App.jsx
```jsx
import React from 'react';
import BmiCalculator from './bmi_calculator';

function App() {
  return (
    <div>
      <BmiCalculator />
    </div>
  );
}

export default App;

```

## OUTPUT

![image](https://github.com/user-attachments/assets/0a908f32-4a3e-48da-8cc5-66a650978e08)

![image](https://github.com/user-attachments/assets/66c472f9-298d-4010-b896-089f69c04050)

![image](https://github.com/user-attachments/assets/f8aa10c1-da7b-4792-af35-58b0d27ccf52)



## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
