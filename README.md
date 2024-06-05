# permeability
Permeability Calculation of Porous Media using PoreSPY and OpenPNM

This Python-based tool calculates the effective permeability of porous media samples from raw micro-CT scan data. It's designed to streamline the analysis of porous materials for applications like oil and gas reservoir characterization, soil science, or materials engineering.

Key Features
Micro-CT Integration: Processes raw micro-CT scan files, transforming voxel information into a 3D representation of the pore space.
Pore Network Reconstruction: Uses PoresPy's SNOW algorithm to generate a 3D pore network model, capturing the connectivity of pores and throats.
OpenPNM Simulation: Leverages OpenPNM to simulate fluid flow through the reconstructed network under Stokes flow conditions.
Permeability Calculation: Calculates effective permeability using Darcy's law, incorporating sample dimensions, voxel size, fluid viscosity, and simulated flow rate.
Cluster Analysis & Trimming: Identifies and analyzes isolated pore clusters, allowing you to remove small clusters that could skew permeability results.
Output: Generates a text file (permeability_results.txt) detailing calculated permeabilities for each sample, along with cluster information.

Installation:

Prerequisites: Ensure you have Python installed on your system.
Install Libraries: Use pip to install the required packages:

pip install numpy openpnm porespy

Usage:

Prepare Data: Place your raw micro-CT scan files (e.g., sample_1.raw, sample_2.raw, etc.) in the project directory.
Input Parameters:
Modify the sample_size variable in the script to match the dimensions of your micro-CT scans in voxels (e.g., (200, 200, 200) for a 200x200x200 voxel scan in z, y, x coordinates).
Modify the voxel_size variable in the script to match the size of each voxel in your scans (in meters).
Run: Execute the Python script: python permeability_calculator.py (or whatever you name it).
Cluster Input: The script will print information about the isolated clusters found in each sample. You will be prompted to enter the size of the largest cluster for each sample. This is important to ensure that the flow simulation considers the main interconnected pore network.
Results: The calculated permeabilities and cluster details will be written to permeability_results.txt.

Important Note
The accuracy of the permeability calculations relies on accurate input of the sample size and voxel size. Make sure to verify these values before running the analysis.

Contributing
Contributions are welcome! Please feel free to open issues, submit pull requests, or provide feedback.

License
This project is licensed under the MIT License - see the LICENSE file for details.
