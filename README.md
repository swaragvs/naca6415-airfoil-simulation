# Simulation Report: Structural and Fluid Flow Analysis of NACA 6415 Airfoil

**Bootcamp:** Drone UAS Technologies Bootcamp  
**Institution:** Mahaguru Institute of Technology, Kattachira  
**Collaboration:** National Institute of Technology (NIT) Calicut  
**Author:** Swarag V S  

---

## **Aim**
To conduct both structural and fluid flow simulation analysis of the airfoil **NACA 6415** using **ANSYS 2025 Student Version** to evaluate its mechanical and aerodynamic performance under standard operating conditions.

---

## **Software Used**
- **ANSYS 2025 Student Version**
  - ANSYS Mechanical (Structural Analysis)
  - ANSYS Fluent (CFD Analysis)

---

# Part I: Structural Analysis

## **1. Preprocessing and Setup in ANSYS Mechanical**

### **a. Geometry Import & Setup**
- Imported 2D NACA 6415 coordinates via coordinate file / DesignModeler.  
- Scaled profile to desired chord length.  
- Extruded to create a 3D airfoil solid.

### **b. Material Assignment**
Materials used:
- Structural Steel  
- Aluminium Alloy (Wrought)

(Material properties taken from ANSYS Engineering Data Library.)

### **c. Coordinate Systems**
- Default global coordinate system retained.

### **d. Meshing**
- Body sizing refinement level: **3**  
- Tetrahedral high-resolution mesh  
- Mesh quality validated for low skewness.

### **e. Static Structural Setup**
- **Analysis Type:** Static Structural (A5)  
- **Time:** 1s (default static case)  

**Boundary Conditions:**
- Fixed Support → root/base surface  
- Pressure Load → uniform pressure on top surface  

### **f. Solution & Post-Processing**
Extracted outputs:
- Total Deformation  
- Directional Deformation (X-axis)  
- Maximum Principal Stress  
- Maximum Shear Stress  

---

## **2. Results (Structural)**

### **a. Total Deformation**
- **Max:** 1.3092e-5 m  
- **Min:** 0 m  

**Image Placeholder:** `images/total_deformation.png`

---

### **b. Directional Deformation (X-Axis)**
- **Max:** 1.2234e-7 m  
- **Min:** -1.7098e-7 m  

**Image Placeholder:** `images/directional_deformation.png`

---

### **c. Max Principal Stress**
- **Max:** 2.1617e5 Pa  
- **Min:** -64435 Pa  

**Image Placeholder:** `images/max_principal_stress.png`

---

### **d. Max Shear Stress**
- **Max:** 74019 Pa  
- **Min:** 15.456 Pa  

**Image Placeholder:** `images/max_shear_stress.png`

---

# Part II: Fluid Flow Analysis (CFD)

## **1. Preprocessing and Setup in ANSYS Fluent**

### **a. Geometry Preparation**
- Imported airfoil into SpaceClaim / DesignModeler  
- Created 2D domain with appropriate boundaries  
- Generated surface body & enclosed domain  

### **b. Meshing**
- Applied face sizing & inflation layers  
- Structured quad grid (or hybrid)  
- Ensured **Y+ < 300**

### **c. Solver Settings**
- Solver: **Pressure-based**, steady-state  
- Model: **Spalart-Allmaras (1-equation turbulence model)**  
- Energy Equation: Disabled  

### **d. Boundary Conditions**
- **Inlet:** 20 m/s (Velocity)  
- **Outlet:** Pressure Outlet (0 Pa)  
- **Wall:** No-slip airfoil surface  

### **e. Reference Values**
- Density: 1.225 kg/m³  
- Viscosity: 1.7894e-5 kg/m·s  
- Reference Area: 1 m²  
- Reference Length: 1 m  
- Temp: 288.16 K  
- Cp: 1.4  

### **f. Initialization**
- Initialized from inlet  
- Convergence criteria: **1e-5**  
- Monitored lift & drag coefficients  

---

## **2. CFD Results**

### **a. Aerodynamic Coefficients**
- **Lift Coefficient (Cl):** 0.450831  
- **Drag Coefficient (Cd):** 0.020241  

**Image Placeholders:**  
- `images/scaled_residuals.png`  
- `images/cl_graph.png`  
- `images/cd_graph.png`

---

### **b. Pressure Coefficient Plot**
- Cp vs chord length (scale factor: 0.5)

**Image Placeholder:** `images/cp_distribution.png`

---

### **c. Contour Visualizations**
- Total Pressure  
- Static Pressure  
- Velocity Magnitude  

**Image Placeholders:**  
- `images/total_pressure.png`  
- `images/static_pressure.png`  
- `images/velocity_magnitude.png`

---

# **Results Summary**

| Parameter | Value |
|----------|-------|
| Total Deformation | 1.3092e-5 m |
| Directional Deformation (X-axis) | ±1.2234e-7 to -1.7098e-7 m |
| Max Principal Stress | 2.1617e5 Pa |
| Min Principal Stress | -64435 Pa |
| Max Shear Stress | 74019 Pa |
| Lift Coefficient (Cl) | 0.450831 |
| Drag Coefficient (Cd) | 0.020241 |

---

# **Conclusion**

A comprehensive multiphysics workflow was executed to validate the NACA 6415 airfoil for UAV applications.

- **Structural Insight:**  
  The airfoil shows negligible deformation and safe stress levels under aerodynamic loading—indicating excellent structural integrity.

- **Aerodynamic Insight:**  
  The obtained Cl/Cd ratio highlights efficient lift generation with low drag. Flow visualization confirmed smooth separation and consistent pressure gradients.

**Overall:**  
The NACA 6415 is well-suited for lightweight drone or glider platforms demanding both high aerodynamic efficiency and structural durability.

---

# **Appendix: Insert the Following Visuals in `/images` Folder**
- Mesh & Geometry screenshots  
- Deformation plots  
- Stress plots  
- Residuals graphs  
- Pressure & velocity contours  
- Cp, Cl, Cd graphs  

---

