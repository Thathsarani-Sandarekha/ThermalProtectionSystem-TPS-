# **Spacecraft Thermal Protection System Optimization**

## **Project Overview**
This repository contains the implementation of a **Multi-Objective Genetic Algorithm (NSGA-II)** for optimizing the **Thermal Protection System (TPS)** of a spacecraft. The goal is to design a TPS that balances three competing objectives:
1. **Minimize Weight**: Reduce the TPS weight to improve fuel efficiency and mission cost-effectiveness.
2. **Maximize Durability**: Ensure the TPS can withstand extreme heat and maintain its integrity over multiple re-entry cycles.
3. **Minimize Cost**: Lower material and manufacturing costs while maintaining system performance.

The repository includes all necessary scripts, and data to reproduce the results.

## **How to Run**

### **Step 1: Clone the Repository**

### **Step 2: Install Dependencies**

### **Step 3: Data Preparation**
The material data is scraped from an online database and processed into training, testing, and GA datasets. Run the data scraping and preprocessing scripts:
```bash
data_scraping.ipynb
dl_prediction.ipynb
expanded_data.ipynb
```

### **Step 4: Train Surrogate Models**

### **Step 5: Run Optimization**

### **Step 6: Analyze Results**
Run
```bash
struc_main.ipynb
```

## **Key Features**

### **1. Multi-Objective Optimization**
- **NSGA-II Algorithm**: Balances weight, durability, and cost trade-offs.
- **Constraints**: Ensures temperature resistance and thickness limits are satisfied.

### **2. Surrogate Modeling**
- Random Forest models predict the objectives (weight, durability, cost) based on material properties and thickness.
- Speeds up optimization by replacing computationally expensive simulations.

### **3. Visualization**
- **Pareto Front**: Displays optimal trade-offs between the objectives.
- **Fitness Evolution**: Tracks improvements across generations.

---

## **Sample Results**

### **Pareto-Optimal Solutions**
| Material Name | Thickness (m) | Weight (kg) | Durability (d) | Cost ($) |
|---------------|---------------|-------------|----------------|----------|
| aluminum fluosilicate (topaz) (2 AlFS.SiO2) (a-axis)    | 0.010001      | 353.465327  | 13.592503      | 3.922933 |
| lithium hydride (lih) (cast gas voids)    | 0.010042         | 25651.949701        | 47.31289            | 463.683653    |
| steel stainless (Cr 12-13 Ni 0-3)    | 0.010001         | 775.505978        | 45.395523            | 5.095864     |

### **Fitness Evolution**
The fitness values for weight, durability, and cost improve significantly over generations, demonstrating effective optimization.

---

## **Technologies Used**

- **Python Libraries**:
  - `scikit-learn`: For training surrogate models (Random Forest).
  - `pymoo`: For implementing the NSGA-II algorithm.
  - `pandas` & `numpy`: For data manipulation and preprocessing.
  - `matplotlib`: For visualizing results.

- **Data Source**: Material properties scraped from the [Thermtest Materials Database](https://thermtest.com/thermal-resources/materials-database).

---

## **How It Works**

1. **Data Scraping & Preprocessing**:
   - Scrapes material properties (e.g., thermal conductivity, density).
   - Adds synthetic features like thickness, weight, and cost.

2. **Surrogate Modeling**:
   - Trains Random Forest models to predict weight, durability, and cost.
   - Models are used to estimate fitness during optimization.

3. **Optimization**:
   - NSGA-II optimizes material selection and thickness.
   - Balances trade-offs between weight, durability, and cost.

4. **Visualization**:
   - Generates a Pareto front to display optimal trade-offs.
   - Tracks fitness evolution across generations.

---

## **Future Work**
- Extend the approach to include additional constraints, such as manufacturing feasibility.
- Integrate more advanced surrogate models (e.g., neural networks) for complex predictions.
- Apply the framework to other multi-objective optimization problems in engineering.

---
