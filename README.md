# TS-PROJECT-001-CALCULATOR

import { log } from "console";
import inquirer from "inquirer";

const answers:{
    numberOne: number
    numberTwo: number
    operator: string    
} = await inquirer.prompt([
    {
        type: "number",
        name: "numberOne",
        message: "Kindly enter your first number"
    },
    {
        type: "number",
        name: "numberTwo",
        message: "kindly enter your second number"
    },
    {
        type: "list",
        name: "operator",
        choices: ["+", "-", "*", "/"],
        message: "Select Operator: "
    },
])

const {numberOne, numberTwo, operator} = answers;

let result
  switch (operator) {
    case "+":
      result = numberOne + numberTwo;
      break;
    case "-":
      result = numberOne - numberTwo;
      break;
    case "*":
      result = numberOne * numberTwo;
      break;
    case "/":
      result = numberOne / numberTwo;
      break;
    default:
      log("Invalid operator");
  }

  log(`${numberOne} ${operator} ${numberTwo} = ${result}`);
