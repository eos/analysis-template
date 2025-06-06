# Analysis AYEAR-AIDX
## Succinct Title of your Analysis

Authors: F. Author, S. Author, ...

### Run the Analysis

The analysis is run within a dedicated analysis container to ensure reproducability.
You should build the container image specifically for your analysis.
Below, we assume that you replace ``ANALYSIS`` with a unique identifier,
e.g. ``2025-01`` or similar.

1. Adjust the file describing the container image, e.g., adjust the EOS version that you require.

2. Build a container image specific to the analysis using ``podman``.

```bash
podman build -f image/Dockerfile -t eos:ANALYSIS ./
```

3. You can now run ``eos-analysis`` within the container using ``podman``, e.g., using
```bash
podman run eos:ANALYSIS \
    --volume $(pwd):/analysis/ \
    eos-analysis run -f analysis.yaml
```

### Contents

#### Ancillary Files

The files in this directory represent inputs and approximations to the results of an EOS-based analysis
of ....

 - ``analysis.yaml``: Definition and description of the entire analysis for use with an interactive Jupyter notebook and/or the ``eos-analysis`` command-line tool.
   - The posterior ``XXX`` provides the nominal results of the analysis.
   - The posteriors ``YYY``, ..., ``ZZZ`` provide supplementary results.
   - The various prediction sets were used to ...

 - ``data``: Posterior samples and posterior-predictive samples produced in the course of the analysis, using EOS version X.Y.Z.
   The samples are stored as ``eos.ImportanceSamples`` and ``eos.Predictions`` objects and can be loaded directly in EOS.

 - ``figures``: Ancillary and supplementary figures produced in the course of the analysis. Both PDF and PNG formats are available.

#### Figures

<table>
<tr>
  <th>Figure</th>
  <th>Caption</th>
</tr>
<tr>
  <th colspan=2>Main Material</th>
</tr>
<tr>
  <td><a href="figures/figure-xyz.pdf?raw=true"><img src="/figures/figure-xyz.png?raw=true" width="1000px" height="auto"></a></td>
  <td>
   First of the main material figures as used in the paper.
   Place here the caption as used in the paper.
   Refer to the posterior labels as <code>XXX</code> or <code>ZZZ</code>.
  </td>
</tr>
<tr>
  <th colspan=2>Supplementary Material</th>
</tr>
<tr>
  <td><a href="figures/figure-abc.pdf?raw=true"><img src="/figures/figure-abc?raw=true" width="1000px" height="auto"></a></td>
  <td>
   First supplementary figure.
  </td>
</tr>
</table>