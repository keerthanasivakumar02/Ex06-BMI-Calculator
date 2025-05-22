# Ex06 BMI Calculator
## Date:20-05-2025

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
# Bm.jsx
```
import React, { useState } from 'react';
import './Bm.css';

function App() {
  const [weight, setWeight] = useState('');
  const [height, setHeight] = useState('');
  const [bmi, setBmi] = useState(null);
  const [message, setMessage] = useState('');

  const calculateBMI = () => {
    if (!weight || !height) {
      alert('Please enter both weight and height');
      return;
    }

    const heightInMeters = height / 100;
    const bmiValue = (weight / (heightInMeters * heightInMeters)).toFixed(2);
    setBmi(bmiValue);

    let msg = '';
    if (bmiValue < 18.5) msg = 'Underweight';
    else if (bmiValue < 24.9) msg = 'Normal weight';
    else if (bmiValue < 29.9) msg = 'Overweight';
    else msg = 'Obese';

    setMessage(msg);
  };

  const resetForm = () => {
    setWeight('');
    setHeight('');
    setBmi(null);
    setMessage('');
  };

  return (
    <div className="App">
      <h1>BMI Calculator</h1>
      <div className="input-group">
        <input
          type="number"
          placeholder="Weight (kg)"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
        />
        <input
          type="number"
          placeholder="Height (cm)"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
        />
      </div>
      <div className="button-group">
        <button onClick={calculateBMI}>Calculate BMI</button>
        <button onClick={resetForm}>Reset</button>
      </div>
      {bmi && (
        <div className="result">
          <h2>Your BMI: {bmi}</h2>
          <p>{message}</p>
        </div>
      )}
    </div>
  );
}

export default App;

```
# Bm.css
```
.App {
  text-align: center;
  font-family: Arial, sans-serif;
  margin-top: 50px;
}

.input-group {
  margin: 20px;
}

.input-group input {
  margin: 10px;
  padding: 10px;
  font-size: 16px;
  width: 200px;
  border: 1px solid #ccc;
  border-radius: 5px;
}

.button-group button {
  margin: 10px;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
  background-color: #0077cc;
  color: white;
  border: none;
  border-radius: 5px;
  transition: background-color 0.3s ease;
}

.button-group button:hover {
  background-color: #005fa3;
}

.result {
  margin-top: 20px;
  font-size: 20px;
}

.result h2 {
  color: #333;
}

.result p {
  font-weight: bold;
  color: #444;
}

body {
  font-family: 'Arial', sans-serif;
  background-color: #02101d;
  display: flex;
  justify-content: center;
  align-items: center;
  height: 100vh;
}
```

## OUTPUT
![image](https://github.com/user-attachments/assets/257b05ca-0765-494a-9be3-65fa918b0f29)

![image](https://github.com/user-attachments/assets/16bd8021-8a29-4214-ba38-d162a73c25d9)

## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
