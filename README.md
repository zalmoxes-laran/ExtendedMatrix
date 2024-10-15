# Extended Matrix official repository

[Official EM website](http://extendedmatrix.org) |
[Telegram open-group](https://t.me/UserGroupEM) |

<!---
![Header](./public/res/header.jpg)
-->

[Extended Matrix](https://www.extendedmatrix.org) -

The Extended Matrix (EM) is a scientific method and formal language for the Cultural Heritage domain. It is based on knowledge graph networks and grounded on FAIR and Open Science principles. EM formalises complex interpretative philological phenomena such as virtual reconstructive hypotheses in a transparent and robust manner; EM enables verifiability of results, reusability of data and collaborative interpretation.

## Citation

You can cite Extended Matrix using the following BibTeX entry:

```
@misc{demetrescu_extendedmatrix_nodate,
 title = {{ExtendedMatrix}},
 copyright = {All rights reserved},
 url = {https://doi.org/10.5281/zenodo.5957132},
 publisher = {Zenodo},
 author = {Demetrescu, Emanuel},
 doi = {10.5281/zenodo.5957132},
}

```

## Extended Matrix Release Notes - Version 1.4

**Release Date:** 2024-10-15

Version 1.4 of the **Extended Matrix** formal language introduces new features aimed at enhancing the ability to describe and formalize surface degradation and transformations over time. Below are the key updates included in this release:

### 1. Addition of the Transformation Static Graphic Unit (TSU) Node

- **Description:** The new **TSU** node has been introduced to formalize and represent static surface degradation phenomena. It enables the description of changes in a stratigraphic unit or physical object, such as walls or other surfaces, affected by long-term degradation processes.
- **Usage:** The TSU node provides a conceptual and visual representation of surface changes over time, facilitating the analysis and interpretation of surfaces that have undergone structural or aesthetic alterations, such as erosion, discoloration, or fragmentation.
- **Benefits:** With the TSU node, users can integrate detailed information about the condition of surfaces, connecting these changes to the broader timeline of an archaeological site or architectural structure.

### 2. Introduction of the Dotted Connector

- **Description:** The new **dotted connector** has been added to link multiple instances of the same stratigraphic unit that has transformed or moved over time. This connector enables users to establish a relationship between different versions of the same element, describing how it evolved or was relocated.
- **Example of Use:** A wall with stratigraphic unit **US100** found in a collapsed state during an excavation can be linked via the dotted connector to **US100B**, representing the same wall relocated to a different position as part of an anastylosis. This preserves the semantic connection between the two instances of the object while acknowledging the change in position or condition over time.
- **Application:** Ideal for representing structural elements or artifacts that have been altered, moved, or reconstructed while maintaining a unique reference to their historical origin.

### 3. General Improvements

- Optimization of temporal queries to incorporate degradation data through **TSU** nodes.
- Enhanced rendering of dotted connections for improved visualization in knowledge graphs.

### 4. Changes in the repo structure

- Removed old 04 EMF folder: the zip files have been moved in the releases section of the GitHub page of the tools (3dsc and EMtools)

**Compatibility:** Version 1.4 is fully compatible with previous versions of Extended Matrix and existing APIs.

For further details on implementation or technical inquiries, please refer to the updated documentation or contact technical support.

## Publications

Main bibliographical reference (open access) of the current version of the EM (1.4) is:

*Scopinaro, Eleonora, Emanuel Demetrescu, e Simone Berto. 2024. «Towards the Definition of Transformation Stratigraphic Unit (TSU) as New Section of the Extended Matrix Methodology». Acta IMEKO 13 (3): 1–9. <https://doi.org/10.21014/actaimeko.v13i3.1830>.*

<!---
You can find [here](url) a complete list of publications where EM was employed in different national and international projects.
-->

## Contribute

You are more than welcome to contribute to the project by spotting bugs/issues and providing code or solutions through pull requests to fix or improve EM functionalities (see TODO list below). Get in touch here on github, through the [telegram open-group](https://t.me/UserGroupEM) or through the other channels.

## TODO list

### EM

- [ ] Alternative hypothesis formalization
- [ ] New metaphors of visualization for anastylosis and virtual restoration
- [ ] Formalization of color maps to visualize statistical data about the reconstruction (volumes, typo of sources, property density)
