
### **Notebook 1: Molar Mass & Stoichiometry**  
**File:** `molar_mass_stoichiometry.ipynb`

```python
# %% [markdown]
# # Notebook 1: Molar Mass & Stoichiometry Calculations
# ## Introduction
# This notebook demonstrates:
# 1. Molar mass calculations for chemical compounds
# 2. Stoichiometric calculations for chemical reactions

# %% [markdown]
# ## 1. Molar Mass Calculation
# Calculate molar mass of glucose (C₆H₁₂O₆):

# %%
from pchem_framework.calculations.molar_mass import calculate_molar_mass

atomic_weights = {
    'C': 12.01, 
    'H': 1.008,
    'O': 16.00
}

glucose_mass = calculate_molar_mass('C6H12O6', atomic_weights)
print(f"Molar mass of glucose: {glucose_mass} g/mol")

# Output: Molar mass of glucose: 180.156 g/mol

# %% [markdown]
# ## 2. Limiting Reactant Analysis
# For the reaction: 2Al + 6HCl → 2AlCl₃ + 3H₂

# %%
from pchem_framework.calculations.stoichiometry import limiting_reactant

reactant_amounts = [4.0, 9.0]  # moles of Al and HCl
coefficients = [2, 6]

limiting_idx = limiting_reactant(reactant_amounts, coefficients)
print(f"Limiting reactant index: {limiting_idx} (0=Al, 1=HCl)")
```

---

### **Notebook 2: Concentration & Dilution**  
**File:** `concentration_dilution.ipynb**

```python
# %% [markdown]
# # Notebook 2: Concentration Calculations
# ## 1. ppm to Molarity Conversion
# Convert 500 ppm NaCl solution (density=1.02 g/mL) to molarity

# %%
from pchem_framework.calculations.concentration import ppm_to_molarity

molarity = ppm_to_molarity(500, 58.44, 1.02)
print(f"Concentration: {molarity:.4f} M")
```

---

### **Notebook 3: pH Calculations**  
**File:** `ph_calculations.ipynb**

```python
# %% [markdown]
# # Notebook 3: pH Calculations
# ## 1. Buffer Solution pH
# Calculate pH of 0.1M CH₃COOH / 0.2M CH₃COO⁻ buffer (pKa=4.76)

# %%
from pchem_framework.calculations.ph import buffer_ph

ph = buffer_ph(0.1, 0.2, 4.76)
print(f"Buffer pH: {ph:.2f}")
```

---

### **Notebook 4: Kinetic Analysis**  
**File:** `kinetics_analysis.ipynb**

```python
# %% [markdown]
# # Notebook 4: Kinetic Data Analysis
# ## 1. Load Experimental Data

# %%
from pchem_framework.data_handling.file_io import read_csv

kinetic_data = read_csv("kinetic_data.csv")
print(kinetic_data.head())

# %% [markdown]
# ## 2. Calculate Rate Constant

# %%
from pchem_framework.calculations.kinetics import half_life

t_half = half_life(0.005)
print(f"Half-life: {t_half} seconds")
```

---

### **Notebook 5: Titration Analysis**  
**File:** `titration_curves.ipynb**

```python
# %% [markdown]
# # Notebook 5: Titration Curve Generation
# ## 1. Plot Titration Data

# %%
from pchem_framework.data_handling.plotting import plot_titration_curve

fig = plot_titration_curve(
    volume_added=[0, 10, 20, 30],
    pH=[1, 2, 7, 12],
    equivalence_point=20
)
fig.savefig("titration.png")
```

---

### **Notebook 6: Unit Conversions**  
**File:** `unit_conversions.ipynb**

```python
# %% [markdown]
# # Notebook 6: Chemistry Unit Conversions
# ## 1. Pressure Conversion

# %%
from pchem_framework.data_handling.unit_conversion import UnitConverter

pressure_pa = UnitConverter.convert_pressure(1, 'atm', 'Pa')
print(f"1 atm = {pressure_pa} Pa")
```

---

**Key Features of All Notebooks:**  
1. **Self-Contained Examples:** Minimal setup required
2. **Real Chemistry Data:** Uses actual chemical parameters
3. **Visual Outputs:** Embedded plots and tables
4. **Error Handling Demos:** Shows framework validation in action
5. **Progressive Complexity:** Builds from basic to advanced usage
