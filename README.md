# 📊 Mean-Variance-Standard Deviation Calculator

A beginner-friendly Python project that uses **NumPy** to compute important statistics (mean, variance, standard deviation, max, min, sum) on a **3×3 matrix**, created from a list of 9 numbers.

> 🎯 This project is perfect for learning NumPy basics and creating clean Python functions with validation and testing.

---

## 📌 Features

- ✅ Validates input list (must be 9 elements)
- ✅ Converts list into a 3x3 matrix
- ✅ Calculates:
  - 📈 Mean
  - 🧮 Variance
  - 📉 Standard Deviation
  - 🔼 Maximum
  - 🔽 Minimum
  - ➕ Sum
- ✅ Returns stats for:
  - 📊 Columns
  - 📋 Rows
  - 🧾 Flattened matrix

---

## 🧪 Example Code

### ✅ Basic Usage

```python
from mean_var_std import calculate

input_data = [0, 1, 2, 3, 4, 5, 6, 7, 8]

result = calculate(input_data)

print("Mean:", result['mean'])
print("Variance:", result['variance'])
print("Standard Deviation:", result['standard deviation'])
print("Max:", result['max'])
print("Min:", result['min'])
print("Sum:", result['sum'])
```

### 📤 Output

```
Mean: [[3.0, 4.0, 5.0], [1.0, 4.0, 7.0], 4.0]
Variance: [[6.0, 6.0, 6.0], [0.666..., 0.666..., 0.666...], 6.666...]
Standard Deviation: [[2.44..., 2.44..., 2.44...], [0.81..., 0.81..., 0.81...], 2.58...]
Max: [[6, 7, 8], [2, 5, 8], 8]
Min: [[0, 1, 2], [0, 3, 6], 0]
Sum: [[9, 12, 15], [3, 12, 21], 36]
```

---

## 🧠 How It Works

```python
def calculate(input_list):
    if len(input_list) != 9:
        raise ValueError("List must contain nine numbers.")
    
    # Reshape list into 3x3 matrix
    matrix = np.array(input_list).reshape(3, 3)

    return {
        'mean': [matrix.mean(axis=0).tolist(), matrix.mean(axis=1).tolist(), matrix.mean().item()],
        'variance': [matrix.var(axis=0).tolist(), matrix.var(axis=1).tolist(), matrix.var().item()],
        'standard deviation': [matrix.std(axis=0).tolist(), matrix.std(axis=1).tolist(), matrix.std().item()],
        'max': [matrix.max(axis=0).tolist(), matrix.max(axis=1).tolist(), matrix.max().item()],
        'min': [matrix.min(axis=0).tolist(), matrix.min(axis=1).tolist(), matrix.min().item()],
        'sum': [matrix.sum(axis=0).tolist(), matrix.sum(axis=1).tolist(), matrix.sum().item()]
    }
```

---

## 🧪 Unit Testing

You can run the provided `test_module.py` file using:

```bash
python -m unittest test_module.py
```

Example test:
```python
from mean_var_std import calculate
import unittest

class TestStats(unittest.TestCase):
    def test_correct_output(self):
        result = calculate([0,1,2,3,4,5,6,7,8])
        self.assertEqual(result['sum'][2], 36)
```

---

## 🗃️ Folder Structure

```
📁 Mean-Variance-Standard Deviation Calculator/
├── main.py             # Run to see output from calculate()
├── mean_var_std.py     # Your main function
├── test_module.py      # Unit tests
└── README.md           # Documentation (this file)
```

---

## 📦 Requirements

- Python 3.6 or above
- NumPy

Install NumPy:
```bash
pip install numpy
```

---

## 📬 Error Handling

```python
>>> calculate([1, 2, 3])
ValueError: List must contain nine numbers.
```

---

## 👨‍💻 Author

**RAGUL**  
_Data Analyst Fresher | Python Enthusiast | Learning Through Projects_  

📫 [GitHub Profile](https://github.com/)  
🔗 [LinkedIn](https://www.linkedin.com/)  
📧 ragulrbtechit@gmail.com

---

## 📄 License

This project is licensed under the [MIT License](https://opensource.org/licenses/MIT). Feel free to use and modify it!

---

## 🙌 Acknowledgment

Built as part of the [freeCodeCamp Scientific Computing with Python Projects](https://www.freecodecamp.org/learn/).

