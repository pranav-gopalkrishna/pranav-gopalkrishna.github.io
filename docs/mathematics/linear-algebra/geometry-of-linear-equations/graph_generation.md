[<< Back to **Geometry of Linear Equations**](https://pranav-gopalkrishna.github.io/mathematics/linear-algebra/geometry-of-linear-equations)

**GRAPH GENERATION**

**_Python code_**

---

```python
import matplotlib.pyplot as plt
import numpy as np
import sys

try:
    arg = sys.argv[1]
except:
    arg = 'row_picture, column_picture'

if 'row_picture' in arg:
    x = np.linspace(-2, 2, 100)
    y_1 = 3 - 2*x
    y_2 = (1 + x)/2
    plt.scatter(1, 1, s=10, color='red', zorder=3)
    plt.plot(x, y_1, label='$2x + y = 3$')
    plt.plot(x, y_2, label='$x - 2y = -1$')
    plt.axhline(y=0, color='k', ls='dashed')
    plt.axvline(x=0, color='k', ls='dashed')
    plt.annotate('(1, 1)', xy=(1.0, 1.0), xytext=(0.9, 2.0), arrowprops=dict(width=2, headwidth=10, headlength=10))
    plt.tight_layout()
    plt.legend()
    plt.show()

if 'column_picture' in arg:
    plt.arrow(0, 0, 2, 1, width=0.005, head_width=0.1, head_length=0.1, length_includes_head=True, color='red', label='$\\vec a$ = [2, 1]')
    plt.arrow(0, 0, 1, -2, width=0.005, head_width=0.1, head_length=0.1, length_includes_head=True, color='blue', label='$\\vec b$ = [1, -2]')
    plt.arrow(0, 0, 3, -1, width=0.005, head_width=0.1, head_length=0.1, length_includes_head=True, color='green', label='$\\vec c$ = [3, -1]')
    plt.tight_layout()
    plt.grid(visible=True)
    plt.axhline(y=0, color='k', ls='dashed')
    plt.axvline(x=0, color='k', ls='dashed')
    plt.legend()
    plt.show()
```