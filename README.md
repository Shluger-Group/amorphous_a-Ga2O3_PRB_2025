# Amorphous Ga₂O₃ structures — Phys. Rev. B 111, 035203 (2025)

Atomic structures of amorphous Ga₂O₃ (a-Ga₂O₃) used in:

> C. Kaewmeechai, J. Strand, and A. Shluger,
> *Electronic structure and properties of trapped holes in crystalline and amorphous Ga₂O₃*,
> Phys. Rev. B **111**, 035203 (2025). https://doi.org/10.1103/PhysRevB.111.035203

Each set contains 20 periodic models of 400 atoms (Ga₁₆₀O₂₄₀). All coordinates are in Å.

## Contents

| Folder | Models | Density (g/cm³) | Cell | Formats |
|---|---|---|---|---|
| `amorphous_Ga2O3_PBE0/` | 20, equilibrium density | 4.71–4.98 (mean 4.84) | triclinic, DFT-relaxed | extended XYZ (`XYZ_format/`), CIF (`CIF_format/`) |
| `fixed_density_Ga2O3_PBE0/` | 20, fixed density | 5.30 | cubic, a = b = c = 16.75 Å | XYZ |

```
amorphous_Ga2O3_PBE0/
├── XYZ_format/ST1.xyz … ST20.xyz     # extended XYZ, lattice vectors in the comment line
├── CIF_format/ST1.cif … ST20.cif
└── structure_details.txt             # cell volume (Å³) and density (g/cm³) per structure
fixed_density_Ga2O3_PBE0/
├── GaO_st1.xyz … GaO_st20.xyz        # plain XYZ; comment line = CP2K optimisation step and total energy (Hartree)
└── structure_details.txt             # cell volume, density and cell vectors
```

**Note:** the fixed-density XYZ files do not contain the cell. Use the cubic cell
a = b = c = 16.75 Å (V = 4699.42 Å³) with periodic boundary conditions, e.g. in ASE:

## How the structures were generated

### Classical molecular dynamics (LAMMPS)

Interatomic potential: rigid-ion version of the potential of M. A. Blanco *et al.*,
Phys. Rev. B **72**, 184103 (2005) (formal charges +3 for Ga and −2 for O).

**Equilibrium-density models** — NPT ensemble, Nosé–Hoover thermostat and barostat, pressure ≈ 0 Pa:

1. 400-atom triclinic supercell of β-Ga₂O₃ equilibrated at 300 K for 50 ps
2. heated to 4000 K at 0.5 K/ps
3. melt equilibrated at 4000 K for 100 ps
4. quenched to 300 K at 1 K/ps
5. equilibrated at 300 K for 50 ps

**Fixed-density models** — NVT ensemble: melted at 4000 K and cooled to 300 K at 1 K/ps
in a cubic cell of 16.75 Å (ρ = 5.30 g/cm³).

### DFT geometry optimisation (CP2K)

| Setting | Value |
|---|---|
| Functional | PBE0-TC-LRC, 30 % exact exchange, truncation radius 5 Å (tuned to the generalised Koopmans' condition) |
| Exact exchange | auxiliary density matrix method (ADMM) |
| Basis sets | DZVP-MOLOPT-SR-GTH (Ga q13, O q6) |
| Pseudopotentials | Goedecker–Teter–Hutter (GTH) |
| Plane-wave cutoff | 600 Ry |
| k-points | Γ-point only |

Equilibrium-density models: atomic positions and cell fully optimised.
Fixed-density models: atomic positions optimised at fixed cell.

## Structural summary

Average coordination numbers (CN) over the 20 models, Ga–O bond cutoff 2.50 Å:

| Set | Ga CN 4 / 5 / 6 (%) | O CN 2 / 3 / 4 (%) | mean Ga–O (Å) |
|---|---|---|---|
| Equilibrium density (4.84 g/cm³) | 55 / 42 / 3 | 8 / 85 / 7 | 1.90 |
| Fixed density (5.30 g/cm³) | 39 / 52 / 9 | 2 / 83 / 15 | 1.93 |

## Citation

If you use these structures, please cite:

```bibtex
@article{Kaewmeechai2025,
  author  = {Kaewmeechai, Chaiyawat and Strand, Jack and Shluger, Alexander},
  title   = {Electronic structure and properties of trapped holes in crystalline and amorphous {Ga$_2$O$_3$}},
  journal = {Phys. Rev. B},
  volume  = {111},
  pages   = {035203},
  year    = {2025},
  doi     = {10.1103/PhysRevB.111.035203}
}
```

## Licence

These data are released under the [Creative Commons Attribution 4.0 International (CC BY 4.0)](https://creativecommons.org/licenses/by/4.0/) licence.

## Contact

Chaiyawat Kaewmeechai — chaiyawat.kaewmeechai.20@ucl.ac.uk
Shluger Group, Department of Physics and Astronomy, University College London
