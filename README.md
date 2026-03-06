## 📖 Table of Contents

- [Overview](#-overview)
- [Live Demo](#-live-demo)
- [Features](#-features)
- [Regression Types Explained](#-regression-types-explained)
- [How to Use](#-how-to-use)
- [Controls Reference](#-controls-reference)
- [Learning Resources](#-learning-resources)
- [Tech Stack](#-tech-stack)
- [Getting Started Locally](#-getting-started-locally)
- [Project Structure](#-project-structure)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🧭 Overview

**3D Regression Lab** is a fully browser-based, interactive educational tool that brings regression analysis to life in three-dimensional space. Instead of reading static equations on a slide, you can:

- **See** how a regression surface bends and twists as you change model parameters
- **Feel** the difference between a flat plane (multiple linear) and a curved mesh (polynomial)
- **Understand** what residuals look like geometrically — not just as a number in a table
- **Experiment** with noise, sample size, and collinearity to build real intuition

It was built to serve one belief: **you don't truly understand something until you can see it move.**

---

## 🚀 Live Demo


### 👉 [**Launch the Interactive 3D Regression Lab →**](https://regression-lab.netlify.app/)

*No installation. No sign-up. Works in any modern browser.*

</div>

| Platform | Status |
|---|---|
| Chrome / Edge | ✅ Fully supported |
| Firefox | ✅ Fully supported |
| Safari | ✅ Fully supported |
| Mobile (touch) | ✅ Touch orbit & pinch-to-zoom |

---

## ✨ Features

### 🎛️ Three Regression Models — Switchable in Real Time

| Model | Formula | Visual Shape |
|---|---|---|
| **Simple Linear** | `y = β₀ + β₁x₁` | Diagonal plane through 3D space |
| **Multiple Linear** | `y = β₀ + β₁x₁ + β₂x₂` | Flat tilted plane |
| **Polynomial Surface** | `y = β₀ + β₁x + β₂x² + …` | Curved mesh surface |

### 📊 Live Parameter Controls

- **Polynomial Degree** — slide from 1 to 5 and watch the surface curve
- **Sample Size (n)** — from 50 to 500 data points
- **Noise Level** — control how scattered the data cloud is
- **Collinearity** — simulate correlated input features
- **Surface Resolution** — adjust mesh density for performance vs. detail

### 🧮 Real-Time Model Metrics

- **RMSE** — Root Mean Squared Error, live-updated on every refit
- **R²** — Coefficient of Determination, color-coded (green = good, orange = poor)

### 🎥 Viewing Modes

- **3D Surface Fit** — see the fitted geometry overlaid on the data cloud
- **Residual Bars** — visualize vertical error lines from each point to the surface
- **Auto Orbit** — smooth automatic camera rotation for presentations

### 🖱️ Full 3D Navigation

| Action | Control |
|---|---|
| Rotate | Left-click + drag |
| Zoom | Scroll wheel |
| Pan | Right-click + drag |
| Touch rotate | Single finger drag |
| Touch zoom | Pinch gesture |

---

## 📐 Regression Types Explained

### 1️⃣ Simple Linear Regression

Finds the best straight line through data with **one input feature**.

```
y = β₀ + β₁ · x₁

β₀  →  intercept (baseline value when x = 0)
β₁  →  slope (how much y changes per unit of x)
```

**Example:** Predicting exam score from hours studied.  
**Visual:** A diagonal plane cutting through the 3D scatter cloud.

---

### 2️⃣ Multiple Linear Regression

Extends simple regression to **two or more input features**, fitting a flat hyperplane.

```
y = β₀ + β₁x₁ + β₂x₂ + … + βₙxₙ

Each βᵢ = effect of xᵢ, holding all other features constant
```

**Example:** Predicting house price from size, bedrooms, and distance to city.  
**Visual:** A flat plane tilted in 3D space at multiple angles simultaneously.

> ⚠️ **Watch for Multicollinearity** — when two features are highly correlated, coefficients become unstable.

---

### 3️⃣ Polynomial Regression

Handles **non-linear relationships** by adding squared and higher-power terms. Still solved as linear regression on engineered features.

```
y = β₀ + β₁x + β₂x² + β₃x³ + … + βₙxⁿ

Degree 2 → parabola   Degree 3 → S-curve   Degree 4+ → complex waves
```

**Example:** Predicting fuel efficiency vs. speed (peaks around 85 km/h, drops at extremes).  
**Visual:** A curved, undulating mesh surface over the data cloud.

> ⚠️ **Overfitting Risk** — high-degree polynomials can memorize training data. Always validate on a held-out test set.

---

## 🕹️ How to Use

### Quick Start

1. **Open the [Live Demo](https://regression-lab.netlify.app/)** in your browser
2. Select a **Regression type** from the dropdown in the left panel
3. Click **Regenerate data** to create a fresh dataset
4. Click **Refit model** to fit the regression
5. Drag the 3D view to explore the geometry from any angle

### Recommended Learning Flow

```
Step 1 → Start with "Simple Linear"
         Set noise to a low value (3–5)
         Notice how the plane perfectly threads through the data cloud

Step 2 → Switch to "Multiple Linear"
         Increase collinearity and observe how the R² changes
         Notice how the plane now tilts in two directions simultaneously

Step 3 → Switch to "Polynomial Surface"
         Increase degree from 2 → 3 → 4
         Enable "Show residual bars" — watch them shrink with higher degree
         Then crank noise up high — notice how the fit degrades

Step 4 → Toggle "Auto Orbit" for a rotating presentation view
```

---

## 🎛️ Controls Reference

| Control | Description | Range |
|---|---|---|
| **Regression type** | Model to fit | Simple / Multiple / Polynomial |
| **Polynomial degree** | Curve complexity (Poly only) | 1 – 5 |
| **Include interaction x₁×x₂** | Add cross-term to polynomial | On / Off |
| **Samples (n)** | Number of data points | 50 – 500 |
| **Noise level** | Standard deviation of random error | 0 – 30 |
| **Collinearity** | Correlation between x₁ and x₂ | 0.00 – 0.99 |
| **Surface resolution** | Mesh grid density | 10 – 60 |
| **Show fitted surface** | Toggle the regression surface mesh | On / Off |
| **Show residual bars** | Toggle vertical error lines | On / Off |
| **Regenerate data** | Create a new random dataset | — |
| **Refit model** | Re-run OLS on current data | — |

---

## 📚 Learning Resources

### 📄 Full Written Guide

A comprehensive step-by-step document covering all three regression methods — with worked examples, analogies, Python code, and an interpretation cheat sheet.

**[⬇️ Download the Complete Regression Guide (DOCX)](./regression_guide.docx)**

Contents:
- ✅ What regression is and why it matters
- ✅ Simple linear regression — hand-calculated worked example
- ✅ Multiple linear regression — house price prediction with 3 features
- ✅ Polynomial regression — fuel efficiency with overfitting analysis
- ✅ Side-by-side comparison table for all three methods
- ✅ 10-step checklist for any regression project
- ✅ Full glossary of key terms in plain English

### 🌐 Further Reading

| Resource | Link |
|---|---|
| Scikit-learn Linear Models | [scikit-learn.org](https://scikit-learn.org/stable/modules/linear_model.html) |
| StatQuest — Regression (YouTube) | [youtube.com/StatQuest](https://www.youtube.com/c/joshstarmer) |
| Khan Academy — Statistics | [khanacademy.org](https://www.khanacademy.org/math/statistics-probability) |
| Three.js Documentation | [threejs.org/docs](https://threejs.org/docs/) |

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| **3D Rendering** | [Three.js r128](https://threejs.org/) — WebGL scene, orbit controls, custom geometry |
| **Regression Engine** | Pure JavaScript — OLS Normal Equation `β = (XᵀX)⁻¹Xᵀy` implemented from scratch |
| **UI / Styling** | Vanilla CSS — glassmorphism design, warm cream aesthetic |
| **Typography** | [DM Serif Display + DM Sans](https://fonts.google.com/) via Google Fonts |
| **Deployment** | Single self-contained HTML file — zero dependencies, zero build step |

### Why No Framework?

The entire application — 3D engine, math engine, and UI — runs in a **single HTML file** with no npm, no bundler, and no server. Just open the file and it works. This makes it:

- ⚡ Instantly shareable (email the file, host anywhere)
- 🔒 Privacy-respecting (no data leaves your browser)
- 📦 Portable (works offline after first load)

---

## 💻 Getting Started Locally

```bash
# Clone the repository
git clone https://github.com/your-username/3d-regression-lab.git

# Navigate to the project folder
cd 3d-regression-lab

# Open directly in your browser — no server needed!
open regression-lab.html          # macOS
start regression-lab.html         # Windows
xdg-open regression-lab.html      # Linux
```

That's it. No `npm install`. No build step. No environment variables.

> For local development with live reload, any simple HTTP server works:
> ```bash
> python3 -m http.server 8000
> # Then visit http://localhost:8000/regression-lab.html
> ```

---

## 📁 Project Structure

```
3d-regression-lab/
│
├── regression-lab.html        # Main application (self-contained)
├── regression_guide.docx      # Full written guide with examples
├── README.md                  # This file
└── LICENSE                    # MIT License
```

### Inside `regression-lab.html`

```
regression-lab.html
├── <style>                    # Full CSS — glassmorphism UI, layout
├── <body>                     # HTML structure — header, panels, canvas
└── <script>
    ├── State management       # Central state object for all parameters
    ├── Data generation        # Synthetic dataset generation with noise & collinearity
    ├── OLS engine             # Matrix operations: matMul, transpose, invertSmall
    ├── Design matrix builder  # Supports simple / multiple / polynomial features
    ├── Three.js scene         # Point cloud, surface mesh, residual lines
    ├── Orbit controls         # Mouse + touch camera navigation
    └── UI bindings            # All sliders, selects, checkboxes, buttons
```

---

## 🤝 Contributing

Contributions are welcome! Ideas for improvement:

- [ ] Add Lasso / Ridge regularization visualization
- [ ] Export fitted model coefficients as JSON
- [ ] Side-by-side comparison mode (two models simultaneously)
- [ ] Animated coefficient-change transitions
- [ ] Real dataset upload (CSV support)
- [ ] Dark / light theme toggle

To contribute:

```bash
# Fork the repo, then:
git checkout -b feature/your-feature-name
# Make changes to regression-lab.html
git commit -m "feat: describe your change"
git push origin feature/your-feature-name
# Open a Pull Request
```

---

## 📄 License

This project is released under the [MIT License](./LICENSE).  
Free to use, modify, and distribute — with attribution appreciated.

---


**Built with curiosity for anyone who wants to see math move.**

![Live Demo](https://regression-lab.netlify.app/)

<br/>

*Made by Vattanac — AI & Data Science Education Series*

</div>
