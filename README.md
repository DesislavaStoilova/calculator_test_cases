# Decision Table Testing for Calculator Application

The repository contains decition table with test cases for a basic Calculator application. It includes simple arithmetic tests, how the calculator should handle invalid inputs, and some special situations (edge cases).

---


## **1. Testing Basic Arithmetic Operations**

This section shows how the calculator should handle basic math operations: addition, subtraction, multiplication, and division with whole and decimal numbers.

| **Number 1**  | **Number 2**  | **Operation** | **What Should Happen**       | **Explanation**                       |
|---------------|---------------|---------------|-------------------------------|---------------------------------------|
| 5             | 3             | +             | 8                             | Add two positive whole numbers.       |
| -5            | -3            | +             | -8                            | Add two negative whole numbers.       |
| 5             | -3            | +             | 2                             | Add one positive and one negative whole number. |
| 0             | 5             | +             | 5                             | Add zero to a whole number.           |
| 5             | 0             | -             | 5                             | Subtract zero from a whole number.    |
| -5            | 3             | -             | -8                            | Subtract a positive whole number from a negative. |
| 5             | 3             | ×             | 15                            | Multiply two positive whole numbers.  |
| -5            | -3            | ×             | 15                            | Multiply two negative whole numbers.  |
| 5             | 0             | ×             | 0                             | Multiply a whole number by zero.      |
| 10            | 2             | ÷             | 5                             | Divide two positive whole numbers.    |
| 10            | 0             | ÷             | Error ("Cannot divide by 0")  | Division by zero is not allowed.      |
| 0             | 5             | ÷             | 0                             | Divide zero by a whole number.        |
| 5.5           | 3.2           | +             | 8.7                           | Add two positive decimal numbers.     |
| -5.1          | -3.4          | +             | -8.5                          | Add two negative decimal numbers.     |
| 5.75          | -3.25         | +             | 2.5                           | Add one positive and one negative decimal. |
| 0             | 5.33          | +             | 5.33                          | Add zero to a decimal.                |
| 5.5           | 0             | -             | 5.5                           | Subtract zero from a decimal.         |
| -5.25         | 3.1           | -             | -8.35                         | Subtract a positive decimal from a negative. |
| 5.2           | 3.4           | ×             | 17.68                         | Multiply two positive decimal numbers.|
| -5.5          | -3.3          | ×             | 18.15                         | Multiply two negative decimals.       |
| 5.0           | 0             | ×             | 0                             | Multiply a decimal by zero.           |
| 10.0          | 2.5           | ÷             | 4.0                           | Divide two positive decimals.         |
| 10.5          | 0             | ÷             | Error ("Cannot divide by 0")  | Division by zero is not allowed.      |
| 0             | 5.25          | ÷             | 0                             | Divide zero by a decimal.             |


---


## **2. Testing Order of Operations**

This section checks if the calculator follows the correct order: parentheses first, then multiplication/division, and finally addition/subtraction with whole and decimal numbers

| **Input**                  | **What Should Happen** | **Explanation**                                |
|----------------------------|------------------------|------------------------------------------------|
| 2 + 3 × 4                  | 14                    | Multiply first, then add (3 × 4 = 12, 12 + 2). |
| (2 + 3) × 4                | 20                    | Parentheses first, then multiply (2 + 3 = 5, 5 × 4). |
| 6 ÷ 2 + 1                  | 4                     | Divide first, then add (6 ÷ 2 = 3, 3 + 1).     |
| 2.5 + 3.2 × 4.1            | 15.62                 | Multiply first, then add (3.2 × 4.1 = 13.12, 13.12 + 2.5). |
| (2.5 + 3.2) × 4.1          | 23.37                 | Parentheses first, then multiply (2.5 + 3.2 = 5.7, 5.7 × 4.1). |
| 6.6 ÷ 2.2 + 1.1            | 4.1                   | Divide first, then add (6.6 ÷ 2.2 = 3, 3 + 1.1). |

---


## **3. Testing Invalid Inputs**

This section tests how the calculator reacts to incorrect inputs like letters or missing numbers.

| **Input**       | **What Should Happen**      | **Explanation**                           |
|-----------------|-----------------------------|-------------------------------------------|
| `abc`           | Error ("Invalid Input")     | Letters or symbols are not allowed.       |
| `12..34`        | Error ("Invalid Input")     | Numbers with two decimal points are wrong. |
| `0007`          | Show as `7`                 | Ignore leading zeros.                     |
| `12 + `         | Error or Wait for Input     | Cannot do math if one number is missing.  |

---


## **4. Testing Chained Calculations**

Chained calculations are when you use the result of one calculation in the next one. For example, you do `2 + 3` and then multiply the result by `4`.

| **Steps**                  | **What Should Happen** | **Explanation**                              |
|----------------------------|------------------------|----------------------------------------------|
| 2 + 3 = × 4                | 20                    | First add (2 + 3 = 5), then multiply (5 × 4). |
| 10 ÷ 2 = + 5               | 10                    | First divide (10 ÷ 2 = 5), then add (5 + 5). |
| 2.5 + 3.5 = × 4.0          | 24.0                  | First add (2.5 + 3.5 = 6.0), then multiply (6.0 × 4.0). |
| 10.5 ÷ 2.5 = + 5.0         | 9.2                   | First divide (10.5 ÷ 2.5 = 4.2), then add (4.2 + 5.0). |

---


## **5. Testing Edge Cases**

Edge cases are unusual situations like very big numbers or very small numbers. This section tests how the calculator handles those cases.

| **Number 1** | **Number 2** | **Operation** | **What Should Happen**       | **Explanation**                         |
|--------------|--------------|---------------|-------------------------------|-----------------------------------------|
| 0.00001      | 0.00002      | +             | 0.00003                      | Handles very small numbers correctly.    |
| -0           | 5            | +             | 5                             | Treats `-0` the same as `0`.             |
| 1e+100       | 1e+100       | +             | Overflow/Error               | Very large numbers may cause an error.   |
| 12           | `null`       | ×             | Error ("Missing Number")      | One number is missing.                   |





