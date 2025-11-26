
ELISA 4-Parameter Logistic (4PL) Standard Curve Analyzer**

A lightweight Python tool for analyzing ELISA standard curve data using a 4-parameter logistic (4PL) model, commonly used in bioassays such as ELISA, MSD, potency assays, and immunoassays.

This mini-project loads standard concentrations and absorbance values from a CSV file, plots the raw data, fits a 4PL model, and saves the resulting curve as a PNG.

Features

 Load standard curve data from a CSV file
 Scatter plot of raw ELISA standard points
 Fit a **4-parameter logistic (4PL)** model:

*a* – minimum asymptote
*b* – Hill slope
*c* – inflection point (EC50)
*d* – maximum asymptote
   Generate a smooth 4PL curve
   Save the fitted curve as a PNG
   Console output of fitted parameters
   Easy to extend (unknown sample calculation coming soon)


Project Structure

```
elisa-analyzer/
│
├── elisa_analyzer.py          # main Python script
├── standards.csv              # sample ELISA standard data
├── elisa_standard_curve.png   # raw scatter + line plot
├── elisa_standard_curve_4pl.png  # fitted 4PL curve
└── README.md
```

---

Example Standard Curve Data**

`standards.csv` contains manually entered example data:

```csv
concentration_ng_ml,absorbance
0,0.05
10,0.12
20,0.20
40,0.39
80,0.79
160,1.55
```

You can replace this with your own ELISA standards.

---

Example Output Plot

(TIP: After pushing, GitHub will show the image automatically.)

```
![4PL Curve](elisa_standard_curve_4pl.png)
```

---

4-Parameter Logistic (4PL) Function

The model used:

[
y = d + \frac{a - d}{1 + \left(\frac{x}{c}\right)^b}
]

* **a** – minimum asymptote
* **d** – maximum asymptote
* **c** – inflection point (EC50)
* **b** – Hill slope

This is the standard equation used in ELISA and potency assays for calculating unknown concentrations.

How to Run

Install dependencies:

```bash
pip install pandas matplotlib scipy
```

Run the script:

```bash
python elisa_analyzer.py
```

 Output:

* Fitted parameters (a, b, c, d)
* Saved plot: `elisa_standard_curve_4pl.png`

---

Technologies Used

* Python 3
* pandas
* NumPy
* SciPy (curve_fit)
* Matplotlib
* Git & GitHub
* PyCharm IDE

---

Future Improvements

Planned enhancements:

* Add unknown sample concentration calculation
* Add inverse 4PL (solve for x from OD)
* Add error bars for replicates
* Add auto-detection of working range
* Add interactive plot via Plotly
* Add GUI (Tkinter or Dash)


