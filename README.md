**Coupled Thermo-Kinetic Modeling for LRS Diagnostic Correction in PMMA Pyrolysis**
This repository contains a specialized 1D transient numerical solver designed to quantify and correct compositional bias in Laser Rayleigh Scattering (LRS) diagnostics. The model specifically addresses the "blowing effect" during the pyrolysis of Poly(methyl methacrylate) (PMMA).

**📌 Project Overview**
Non-intrusive temperature measurement near pyrolyzing surfaces is often skewed because fuel vapor displaces the calibration gas (e.g., Helium). This displacement changes the effective Rayleigh cross-section ($\sigma_{mix}$), leading to errors as high as 650 K.This tool uses the Method of Lines (MOL) to couple:Solid-Phase: 1D Transient heat conduction with Arrhenius pyrolysis kinetics.Gas-Phase: Species transport (Fuel vapor, Helium tracer, and Air) with convective "blowing" boundaries.Key Capabilities:Bias Quantification: Generates time-dependent $\sigma_{mix}$ history.Parametric Studies: Simulates responses across heat fluxes (10–40 kW/m²) and varying injection velocities ($V_{inj}$).De-biasing: Provides correction factors to recover true thermodynamic temperatures from raw optical data.

🚀 Getting StartedPrerequisites
MATLAB (R2021a or later recommended).No additional toolboxes are strictly required as the solver utilizes the built-in ode15s for stiff differential equations.InstallationClone the repository:Bashgit clone https://github.com/yourusername/Helium-PMMA-Simulation.git

Open MATLAB and navigate to the project folder.Running the SimulationTo reproduce the results mentioned in the associated research article:Main Simulation: Run Main_Coupled_Simulation.m to see a single case thermal and species evolution.Parametric Study: Run Parametric_Analysis.m to generate comparative plots for varying heat fluxes ($q''_{ext}$) and injection velocities ($V_{inj}$).Surface Temperature Rise: Run Main_Simulation.m for a simplified 1D heat conduction view.

📂 Repository Structure
Main_Coupled_Simulation.m: The primary driver for the coupled gas-solid model.Coupled_MOL.m: The core derivative function containing the ODE system.Gas_Species_MOL.m: Species transport logic for Helium and MMA vapor.Pyrolysis_MOL.m: Solid-phase energy balance and Arrhenius kinetics.get_initial_X_profile.m: Finite Difference solver to establish steady-state pre-pyrolysis gas profiles.

📊 Results and Validation
The model captures the "kinetic switch" behavior of PMMA. A key finding included in this code is the sharp drop of Helium mole fraction ($X_{He}$) from 1.0 to $<0.05$ upon pyrolysis onset, proving the dominance of fuel blowing.

📜 LicenseThis project is licensed under the MIT License - see the LICENSE file for details.

✍️ Authors
1. Avijit Mallik - Lead Researcher - avijitme13@gmail.com
2. Mohammad Rahat Rahman
3. Md. Nuruzzaman
   
🎓 Citation
If you use this code in your research, please cite: Mallik, A.; Rahman, M. R. & Nuruzzaman, Md. (2026). Coupled Thermo-Kinetic Modeling for Compositional Bias Correction in Laser Rayleigh Scattering Diagnostics of PMMA Pyrolysis.
