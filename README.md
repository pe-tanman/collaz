# 🔢 Collatz Variations (コラッツ予想の変形)

> *What happens to the Collatz conjecture if you flip the signs?*

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![Jupyter](https://img.shields.io/badge/Jupyter-F37626?logo=jupyter&logoColor=white)
![pandas](https://img.shields.io/badge/pandas-150458?logo=pandas&logoColor=white)


## 🌟 Highlights

- 🧮 **Six rule variants** — the classic *÷2 / ×3+1* plus five sign-flipped cousins
- 📉 **200,000 starting values** — every integer from −100,000 to 99,999
- 📊 **Statistics** — mean and standard deviation of the number of steps to reach 1
- 🔍 **Prime-count curiosity** — how often the step count itself is a prime number
- 🚫 **"Uncomputable" numbers** — which inputs never reach 1 within 1,000 steps


## ℹ️ Overview

The [Collatz conjecture](https://en.wikipedia.org/wiki/Collatz_conjecture) says that if you repeatedly halve even numbers and send odd numbers to `3n + 1`, every positive integer eventually reaches 1.

This notebook generalizes the rule to `(a, b, c)`: divide even numbers by `a`, and send odd numbers to `b·n + c`. It then compares six sign combinations over negative and positive inputs:

| Variant | Even step | Odd step |
| --- | --- | --- |
| `(2, 3, 1)` *(classic)* | n ÷ 2 | 3n + 1 |
| `(2, 3, −1)` | n ÷ 2 | 3n − 1 |
| `(−2, 3, 1)` | n ÷ −2 | 3n + 1 |
| `(−2, 3, −1)` | n ÷ −2 | 3n − 1 |
| `(−2, −3, 1)` | n ÷ −2 | −3n + 1 |
| `(−2, −3, −1)` | n ÷ −2 | −3n − 1 |

Each variant gets a scatter plot of *starting value vs. steps to reach 1*, plus summary statistics.


### ✍️ Author

A 2022 math exploration by [Yuki Ishihara](https://github.com/pe-tanman).


## 🚀 Usage

```bash
git clone https://github.com/pe-tanman/collaz.git
cd collaz
pip install numpy pandas matplotlib jupyter
jupyter notebook "コラッツ/collaz.ipynb"
```

Run the cells from top to bottom. Plots are saved as `y1.png` … `y6.png`, and a random sample of results goes to `to_csv_out.csv`.

> [!TIP]
> Generating all six variants over 200,000 inputs takes a while. Shrink the `range(-100000, 100000)` in the first cell for a quick run.
