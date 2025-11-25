# Ex06 BMI Calculator
## Date:

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
### App.js:
```
import { useState } from "react";
import "./App.css";

function App() {
  const [height, setHeight] = useState("");
  const [weight, setWeight] = useState("");
  const [bmi, setBmi] = useState(null);
  const [message, setMessage] = useState("");

  const calculateBMI = () => {
    if (height === "" || weight === "") {
      alert("Please enter both height and weight");
      return;
    }

    const h = height / 100;
    const calc = weight / (h * h);
    setBmi(calc.toFixed(2));

    if (calc < 18.5) setMessage("Underweight");
    else if (calc >= 18.5 && calc < 24.9) setMessage("Normal weight");
    else if (calc >= 25 && calc < 29.9) setMessage("Overweight");
    else setMessage("Obesity");
  };

  return (
    <div className="container">
      <h1>BMI Calculator</h1>

      <div className="input-group">
        <label>Height (cm)</label>
        <input
          type="number"
          placeholder="Enter height"
          value={height}
          onChange={(e) => setHeight(e.target.value)}
        />
      </div>

      <div className="input-group">
        <label>Weight (kg)</label>
        <input
          type="number"
          placeholder="Enter weight"
          value={weight}
          onChange={(e) => setWeight(e.target.value)}
        />
      </div>

      <button onClick={calculateBMI}>Calculate BMI</button>

      {bmi && (
        <div className="result">
          <h2>Your BMI: {bmi}</h2>
          <p>{message}</p>
        </div>
      )}

      <footer>
        <p>Created by: YOUR NAME – REGISTER NUMBER</p>
      </footer>
    </div>
  );
}

export default App;
```
### App.css:
```
body {
  background: #f2f2f2;
  font-family: Arial, Helvetica, sans-serif;
}

.container {
  max-width: 400px;
  margin: 50px auto;
  padding: 25px;
  background: #fff;
  border-radius: 10px;
  box-shadow: 0px 0px 10px #ccc;
  text-align: center;
}

.input-group {
  margin-bottom: 20px;
  text-align: left;
}

label {
  font-weight: bold;
}

input {
  width: 100%;
  padding: 10px;
  margin-top: 8px;
  border: 1px solid #999;
  border-radius: 5px;
}

button {
  width: 100%;
  padding: 12px;
  background: #007bff;
  color: white;
  border: none;
  border-radius: 5px;
  cursor: pointer;
  font-size: 16px;
}

button:hover {
  background: #0056b3;
}

.result {
  margin-top: 20px;
  background: #e9ffe9;
  padding: 15px;
  border-radius: 5px;
}

footer {
  margin-top: 30px;
  font-size: 14px;
  color: #555;
}
```

## OUTPUT


## RESULT
The program for creating BMI Calculator using React Router is executed successfully.
