# xplendid

This module aims to make it easier for data scientists, analysts, and engineers to conduct statistically sound experiments. At its core is lies the `ABTesting` class. This class provides tools for designing, analyzing, and simulating A/B tests.

---

## Features

- **Sample Size Calculation**: Calculate the minimum required sample size using Evan Miller's methodology.
- **Result Analysis**: Retrieve and visualize experiment results with support for confidence intervals and kernel density estimates (KDEs).
- **Recommendation**: Generate results summary and recommendations based os results.

---

## Dependencies

The following Python libraries are required:

```python
import scipy.stats as scs
import numpy as np
import plotly.graph_objects as go
import pandas as pd
```

---

## Class Overview

### `ABTesting`
The main class provides the following methods and attributes:

#### **Initialization**
```python
ABTesting(bcr, mde, alpha = 0.05, power = 0.8, is_absolute_variation: bool = True, is_two_tailed: bool = True)
```

- **bcr**: Baseline Conversion Rate (0 <= mde < 1).
- **mde**: Minimum Detectable Effect (absolute or relative) (0 < mde < 1).
- **alpha**: Significance level (default: 0.05).
- **power**: Statistical power (default: 0.8).
- **is_absolute_variation**: Whether `mde` is absolute (default: True).
- ** is_two_tailed**: Use two-tailed tests (default: True).

#### **Methods**

1. **`evan_miller_sample_size()`**
   - Calculates the required sample size using Evan Miller's methodology.

3. **`get_experiment_results(n_ctrl, p_ctrl, n_trmt, p_trmt, plot_type = 'KDE')`**
   - Analyzes and visualizes results.
   - Parameters:
     - `n_ctrl`, `n_trmt`: Sample sizes of the control and treatment groups.
     - `p_ctrl`, `p_trmt`: Conversion rates for control and treatment groups.
     - `plot_type`: for visualization(`'KDE'` or `'Confidence Intervals'`) or results summary and recommendations (None).

---

## Usage

### Cloning the repository

**`git clone https://github.com/domingosdeeulariadumba/explendid.git`**


### Importing the module

```python
from xplendidLab import ABTesting
```

### Example: Calculate Sample Size
```python
ab_test = ABTesting(bcr = 0.1, mde = 0.02, alpha = 0.05, power = 0.8)
sample_size = ab_test.evan_miller_sample_size()
print(f"Required Sample Size: {sample_size}")
```

### Example: Visualize Experiment Results
```python
ab_test.get_experiment_results(n_ctrl = 500, p_ctrl = 0.1, n_trmt = 500, p_trmt = 0.12, plot_type = 'Confidence Intervals')
```

💡 A more detailed example regarding the implementation of this tool is available <em> <a href = 'https://github.com/domingosdeeulariadumba/xplendid/blob/master/xplendidExamplesNotebook.ipynb' target = '_blank'> here.</em> 

---

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

---

## Contribution

Contributions are welcome! Please fork the repository, create a feature branch, and submit a pull request.



---

## References
- FÁVERO, L. P.; BELFIORE, P. <em> <a href = 'https://www.amazon.com.br/Manual-An%C3%A1lise-Dados-Luiz-F%C3%A1vero/dp/8535270876' target = '_blank'> Manual de Análise de Dados: estatística e modelagem
multivariada com Excel®, SPSS® e Stata®.</em> Rio de Janeiro: Elsevier, 2017.
- GRAVETTER, F. J.; WALLNAU, L. B. <em> <a href = 'https://www.amazon.com/Statistics-Behavioral-Sciences-Standalone-Book/dp/1305504917' target = '_blank'> Statistics for the Behavioral Sciences.</em> 10th ed. Boston:
Cengage Learning, 2015.
- SAINANI K. Stanford University. <em> <a href = 'https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://web.stanford.edu/~kcobb/hrp259/lecture11.ppt&ved=2ahUKEwin0_6qmsuKAxVHUEEAHSzNEt0QFnoECBUQAQ&usg=AOvVaw16arOYUy8mK6FcYHGblX0m' target = '_blank'> Introduction to Sample Size and Power Calculations</em>. Last accessed on Dec 28 2024.
- UDACITY. <em> <a href = 'https://www.udacity.com/course/ab-testing--ud257' target = '_blank'> A/B Testing</em>. Last accessed on Dec 28 2024.
  
---
## Acknowledgments

This project would not be possible without the massive contribution of Evan Miller regarding A/B testing methodologies and tools. Refer to his <em> <a href = 'https://www.evanmiller.org/ab-testing/sample-size.html' target = '_blank' a> A/B Testing Sample Size Calculator</em> for further details.

---
## Explore the Web App 🌐🚀

Try the   <img src = 'https://i.postimg.cc/XJ38H6RZ/xplendid-logo-rect.png' width = '70' height = '35'/>   **[web service](https://xplendid.onrender.com)**.


## Networking

Connect with me:

<img src = 'https://i.postimg.cc/wj3w1mjG/kofi-icon.png' width = '25' height = '25'/>  **[/domingosdeeulariadumba](https://ko-fi.com/domingosdeeulariadumba)**

<img src = 'https://i.postimg.cc/t4vNmLB0/linktree-icon.png' width = '25' height = '25'/>  **[/domingosdeeulariadumba](https://linktr.ee/domingosdeeulariadumba)**

<img src = 'https://i.postimg.cc/W1178266/linkedin-icon.png' width = '25' height = '25'/>  **[/domingosdeeulariadumba](https://linkedin.com/in/domingosdeeulariadumba/)**