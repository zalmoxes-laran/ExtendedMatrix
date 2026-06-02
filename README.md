# Extended Matrix official repository

[Official EM website](https://extendedmatrix.org) |
[Telegram open-group](https://t.me/UserGroupEM) |

<!---
![Header](./public/res/header.jpg)
-->

[Extended Matrix](https://www.extendedmatrix.org) -

The Extended Matrix (EM) is a scientific method and formal language for the Cultural Heritage domain. It is based on knowledge graph networks and grounded on FAIR and Open Science principles. EM formalises complex interpretative philological phenomena such as virtual reconstructive hypotheses in a transparent and robust manner; EM enables verifiability of results, reusability of data and collaborative interpretation.

> **This branch tracks the EM 1.5 release line — the current Long-Term Support (LTS) recommendation for new Extended Matrix projects.**

## Latest release: 1.5.0

EM 1.5.0 was released on **2026-05-15** and is the recommended starting point for all new Extended Matrix projects. EM 1.4 LTS remains available on the `EM_v1.4` branch for legacy projects already authored against it.

- **EM Tools 1.5.0** (Blender add-on) — pick the build for your Blender + OS combo from the [EM Tools download page](https://extendedmatrix.org/tools/em-tools/).
- **Manual** — read the EM 1.5 manual at [docs.extendedmatrix.org/en/1.5.0/](https://docs.extendedmatrix.org/en/1.5.0/).
- **What's new in 1.5** — the full write-up on language, tools and methodology changes lives on the EM site: [extendedmatrix.org/versions/1-5/](https://extendedmatrix.org/versions/1-5/).
- **Project home** — [extendedmatrix.org](https://extendedmatrix.org).

## Documentation

The Extended Matrix manual for 1.5 is published at [docs.extendedmatrix.org/en/1.5.0/](https://docs.extendedmatrix.org/en/1.5.0/). The same documentation site hosts the companion tools' manuals — see [EM Tools docs](https://docs.extendedmatrix.org/projects/EM-tools/en/latest/) and the [s3Dgraphy docs](https://docs.extendedmatrix.org/projects/s3dgraphy/) for the Blender add-on and the Python library respectively.

## Ecosystem

EM 1.5 is supported by three companion components:

- **[EM Tools](https://extendedmatrix.org/tools/em-tools/)** — Blender add-on that turns an EM graph into an interactive 3D scene: stratigraphy and proxy managers, epoch-aware visualisation, Document Manager, Representation Models manager, CronoFilter and Heriverse export. Source: [zalmoxes-laran/EM-blender-tools](https://github.com/zalmoxes-laran/EM-blender-tools).
- **[s3Dgraphy](https://extendedmatrix.org/tools/s3dgraphy/)** — standalone Python library for reading, writing and querying EM graphs outside Blender (`pip install s3dgraphy`). In 1.4 the code was bundled inside EM Tools; from 1.5 it ships on PyPI as its own component. Source: [zalmoxes-laran/s3dgraphy](https://github.com/zalmoxes-laran/s3dgraphy).
- **[3D Survey Collection (3DSC)](https://extendedmatrix.org/tools/3dsc/)** — survey-to-mesh pipeline that feeds the EM proxy workflow. The Blender add-on (3DSC 1.7.0) is paired with [3DSC for Metashape](https://extendedmatrix.org/tools/3dsc-metashape/) for the photogrammetric side. Source: [zalmoxes-laran/3D-survey-collection](https://github.com/zalmoxes-laran/3D-survey-collection).

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

## Publications

EM 1.5 is fully backward-compatible with 1.4, and the main bibliographical reference of the 1.4 LTS line — open access — remains valid as the current methodological reference for the formalism. A dedicated 1.5 reference paper is in preparation.

*Scopinaro, Eleonora, Emanuel Demetrescu, e Simone Berto. 2024. «Towards the Definition of Transformation Stratigraphic Unit (TSU) as New Section of the Extended Matrix Methodology». Acta IMEKO 13 (3): 1–9. <https://doi.org/10.21014/actaimeko.v13i3.1830>.*

<!---
You can find [here](url) a complete list of publications where EM was employed in different national and international projects.
-->

## Contribute

You are more than welcome to contribute to the project by spotting bugs/issues and providing code or solutions through pull requests to fix or improve EM functionalities. Get in touch here on github, through the [Telegram open-group](https://t.me/UserGroupEM) or through the other channels.

## Roadmap

EM 1.6 is in active development on the `EM_v1.6.dev` branch. Ongoing work, formalised as Development Projects, is tracked at [dev.extendedmatrix.org](https://dev.extendedmatrix.org/). Headline items currently in the pipeline include US image resources and the Image Viewing System (deferred from 1.5), the boolean + LOD surface-proxy strategy, full georeferencing via `GeoPositionNode`, and broader Landscape / Mobile Object graph constructs.
