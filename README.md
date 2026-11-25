<h1 align="center">BUAN bundle shapes</h1>

<p align="center">
  Shape similarity between bundles of the same type across a population, with the DIPY BUAN (bundle analytics) workflow.
</p>

<p align="center">
  <a href="https://github.com/brainlife/abcd-spec"><img src="https://img.shields.io/badge/ABCD_Spec-v1.1-green.svg" alt="ABCD Spec v1.1"></a>
  <a href="https://doi.org/10.25663/brainlife.app.455"><img src="https://img.shields.io/badge/Brainlife-brainlife.app.455-blue.svg" alt="Run on brainlife.io"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/License-MIT-lightgrey.svg" alt="MIT license"></a>
</p>

## At a glance

<!-- brainlife-app:begin (generated from the App manifest; edit the manifest, not this block) -->

> **Computes shape similarity between bundles of the same type across subjects with the DIPY BUAN (bundle analytics) dipy_buan_shapes workflow.**

Wraps dipy_buan_shapes, which finds shape similarity between input bundles of the same type across a population, as described in Chandio et al. 2020. The code reads clust_thr, threshold and subject_folder from config.json, but no inputs or parameters are registered for this App.

| | |
|---|---|
| **Container** | `brainlife/dipy:1.1.1` |
| **Resources** | 8 CPUs |
| **Run it** | [doi.org/10.25663/brainlife.app.455](https://doi.org/10.25663/brainlife.app.455) |

<!-- brainlife-app:end -->

## Running the App

### On brainlife.io

The App is registered at [doi.org/10.25663/brainlife.app.455](https://doi.org/10.25663/brainlife.app.455) and is one of the [DIPY Apps on brainlife.io](https://brainlife.io/apps#dipy). It wraps the DIPY command-line workflow [`dipy_buan_shapes`](https://dipy.org/documentation/1.2.0./interfaces/buan_flow/), which finds shape similarity between input bundles of the same type across populations, implementing the bundle shape similarity method of Bundle Analytics (Chandio et al. 2020). The code reads `subject_folder`, `clust_thr` and `threshold` from `config.json`; no inputs or parameters are currently registered for the App on brainlife.io.

### Locally

You need [Singularity/Apptainer](https://apptainer.org/) and [`jq`](https://jqlang.github.io/jq/). DIPY 1.1.1 runs inside the container.

1. Clone this repository and check out the branch brainlife.io runs: `git checkout 1.1.1`.
2. Create `config.json` with the folder of subject bundles and the BUAN options:

   ```json
   {
       "subject_folder": "test_data/subjects",
       "clust_thr": "5 3 1.5",
       "threshold": 6
   }
   ```

3. Run the App:

   ```bash
   ./main
   ```

You can also call the workflow directly; see the [`dipy_buan_shapes` reference](https://dipy.org/documentation/1.2.0./interfaces/buan_flow/) for all arguments:

```bash
singularity exec -e docker://brainlife/dipy:1.1.1 dipy_buan_shapes [your_args]
```

## Outputs

```text
output/   results of dipy_buan_shapes (bundle shape similarity across subjects)
```

## Citing

> [!TIP]
> If you use this App in your work, please cite the App, the software it builds on and brainlife.io (below). GitHub's **Cite this repository** button gives the App citation in APA and BibTeX.

- Chandio BQ, et al. Bundle analytics, a computational framework for investigating the shapes and profiles of brain pathways across populations. *Scientific Reports* 10:17149 (2020).
- BUAN Compute Bundles Shapes . brainlife.io App. [doi:10.25663/brainlife.app.455](https://doi.org/10.25663/brainlife.app.455)
- Chandio BQ, et al. Bundle analytics, a computational framework for investigating the shapes and profiles of brain pathways across populations. Scientific Reports 10, 17149 (2020).
- Garyfallidis et al. Dipy, a library for the analysis of diffusion MRI data. *Frontiers in Neuroinformatics* 8 (2014). [doi:10.3389/fninf.2014.00008](https://doi.org/10.3389/fninf.2014.00008)
- Hayashi S, Caron BA, Heinsfeld AS, et al. brainlife.io: a decentralized and open-source cloud platform to support neuroscience research. *Nature Methods* 21:809–813 (2024). [doi:10.1038/s41592-024-02237-2](https://doi.org/10.1038/s41592-024-02237-2)
- Avesani P, McPherson B, Hayashi S, et al. The open diffusion data derivatives, brain data upcycling via integrated publishing of derivatives and reproducible open cloud services. *Scientific Data* 6:69 (2019). [doi:10.1038/s41597-019-0073-y](https://doi.org/10.1038/s41597-019-0073-y)

## Authors

- [Bramsh Chandio](https://github.com/BramshQamar)

## Funding

[![Wellcome-226486/Z/22/Z](https://img.shields.io/badge/Wellcome-226486%2FZ%2F22%2FZ-purple.svg)](https://wellcome.org/)
[![NIH-NINDS-U24NS140384](https://img.shields.io/badge/NIH_NINDS-U24NS140384-green.svg)](https://reporter.nih.gov/project-details/11261037)
[![NIH-NINDS-UM1NS132207](https://img.shields.io/badge/NIH_NINDS-UM1NS132207-green.svg)](https://reporter.nih.gov/project-details/11411328)
[![NIH-NIBIB-R01EB029272](https://img.shields.io/badge/NIH_NIBIB-R01EB029272-green.svg)](https://reporter.nih.gov/project-details/10262925)
[![NIH-NIBIB-R01EB030896](https://img.shields.io/badge/NIH_NIBIB-R01EB030896-green.svg)](https://reporter.nih.gov/project-details/10428625)
[![NIH-NIMH-R01MH126699](https://img.shields.io/badge/NIH_NIMH-R01MH126699-green.svg)](https://reporter.nih.gov/project-details/10460628)
[![NIH-NIDCD-R01DC020088](https://img.shields.io/badge/NIH_NIDCD-R01DC020088-green.svg)](https://reporter.nih.gov/project-details/11140284)
[![NSF-BCS-1734853](https://img.shields.io/badge/NSF_BCS-1734853-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1734853)
[![NSF-BCS-2203524](https://img.shields.io/badge/NSF_BCS-2203524-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2203524)
[![NSF-IIS-1636893](https://img.shields.io/badge/NSF_IIS-1636893-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1636893)
[![NSF-OAC-2148729](https://img.shields.io/badge/NSF_OAC-2148729-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2148729)
[![NSF-IIS-1912270](https://img.shields.io/badge/NSF_IIS-1912270-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1912270)
[![NSF-IIS-2148700](https://img.shields.io/badge/NSF_IIS-2148700-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=2148700)
[![NSF-OAC-1916518](https://img.shields.io/badge/NSF_OAC-1916518-blue.svg)](https://www.nsf.gov/awardsearch/showAward?AWD_ID=1916518)

<sub>brainlife.io is publicly funded, and acknowledging that support helps keep it running. This App was developed with support from Wellcome, the U.S. National Institutes of Health (including the BRAIN Initiative BRAIN CONNECTS program: The Axonal Projectome EXchange, U24NS140384, and the Center for Mesoscale Connectomics, UM1NS132207) and the U.S. National Science Foundation.</sub>

## License

[BSD 3-Clause](LICENSE). DIPY is distributed under the terms of the BSD license; see its [LICENSE file](https://github.com/dipy/dipy/blob/master/LICENSE).
