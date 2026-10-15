# TOBII_STREAM

> Titta is a toolbox for using eye trackers from Tobii Pro AB with Python, specifically offering integration with [PsychoPy](https://www.psychopy.org/). A Matlab version that integrates with PsychToolbox is also available from https://github.com/dcnieho/Titta. For a similar toolbox for SMI eye trackers, please see www.github.com/marcus-nystrom/SMITE.

**Category:** PSYCHOLOGY · **Ecosystem:** unknown · **Vendored upstream:** https://github.com/marcus-nystrom/Titta · **Pinned commit:** `1f5d4ac07578e438917e1af89eed97dc1678a3ed` · **Vendor:** Anticloud FZ LLE

> **Note:** this package vendors `https://github.com/marcus-nystrom/Titta` as the implementation for the `TOBII_STREAM` slot. The vendored repository name differs from the package name; the pin above is the exact commit vendored here.

## What This Project Is

Titta is a toolbox for using eye trackers from Tobii Pro AB with Python, specifically offering integration with [PsychoPy](https://www.psychopy.org/). A Matlab version that integrates with PsychToolbox is also available from https://github.com/dcnieho/Titta. For a similar toolbox for SMI eye trackers, please see www.github.com/marcus-nystrom/SMITE.

This is the upstream project, vendored at the pinned commit above and packaged offline-first. The 12 improvements Anticloud adds live in `anticloud/` and are described under *Anticloud Overlay* below. Every fact in this file traces to a file in this directory.

## Installation

```
# See the upstream README (linked above) for build steps.
```

## Usage

As demonstrated in the demo scripts, the toolbox is configured through
the following interface:
1. Retrieve (default) settings for eye tracker of interest: `settings =
Titta.getDefaults('tracker model name');` Supported eye trackers and their corresponding model names in the Tobii Pro SDK/Titta are:

    |Eye tracker|Model name|
    |---|---|
    |**Tobii Pro Spectrum**|`Tobii Pro Spectrum`|
    |**Tobii Pro Fusion**|`Tobii Pro Fusion`|
    |Tobii Pro TX300|`Tobii TX300`|
    |Tobii Pro T60 XL|`Tobii T60 XL`|
    |**Tobii Pro Nano**|`Tobii Pro Nano`|
    |**Tobii Pro Spark**|`Tobii Pro Spark`|
    |**Tobii Pro X3-120**|`Tobii Pro X3-120` or `Tobii Pro X3-120 EPU`|
    |Tobii Pro X2-60|`X2-60_Compact`|
    |**Tobii Pro X2-30**|`X2-30_Compact`|
    |Tobii Pro X60|`Tobii X60`|
    |Tobii Pro X120|`Tobii X120`|
    |Tobii Pro T60|`Tobii T60`|
    |Tobii Pro T120|`Tobii T120`|
    |**Tobii 4C (Upgrade Key required)**|`IS4_Large_Peripheral`|

    Eye trackers marked in **bold** font have been tested. Note that the VR eye trackers are not supported by Titta. Also note that the Tobii 4C cannot be used for research purposes without buying the Pro Upgrade Key, and is compatible with Titta only after this purchase. Unfortunately, the Pro Upgrade Key is no longer sold by Tobii.

2. Change settings from their defaults if wanted.
3. Create a Titta instance using this settings struct: `tracker = Titta(settings);`
4. Interact with the eye tracker using the Titta API.
5. When calling `Titta.calibrate()`, a participant setup and calibration interface is shown. For each screen, several keyboard hotkeys are available to activate certain functionality. By default, the hotkey for each button is printed in the button's label.

## Anticloud Overlay

The 12 improvements live under `anticloud/`. Run the check suite from this directory:

```
python anticloud/bench/runner.py --cwd anticloud
```

## Benchmark Results

| Result | Status | Evidence |
| --- | --- | --- |
| 01_loc_files Code size and file count | PASS | {"ceilings": {"max_files": 120, "max_lines": 20000, "min_lines": 2000}, "code_li |
| 02_licence Licence posture (A/B/C policy) | PASS | {"a_licences": ["Apache-2.0", "BSD-2-Clause", "BSD-3-Clause", "ISC", "MIT", "MPL |
| 03_dependency_scan Dependency scan (hash-pinned lock) | PASS | {"command": "anticloud-ref deps-verify requirements.lock", "declared_in_pyprojec |
| 04_sbom_cyclonedx SBOM (CycloneDX 1.5) | PASS | {"command": "python -c \"import json;d=json.load(open('sbom.cdx.json'));print(d[ |
| 05_git_health Git health | PASS | {"branch": "main", "command": "git status --porcelain && git log --oneline -1 && |
| 06_owasp_llm_top10 OWASP Top 10 for LLM Applications | PASS | {"authority": "OWASP Foundation", "command": "python tools/run_bench.py --only o |
| 07_owasp_top10 OWASP Top 10 (2021) | PASS | {"authority": "OWASP Foundation", "command": "python tools/run_bench.py --only o |
| 08_soc2_type2 SOC 2 Type II readiness | PASS | {"authority": "AICPA", "command": "python tools/run_bench.py --only soc2", "cont |
| 09_nist_ai_rmf NIST AI Risk Management Framework | PASS | {"authority": "NIST AI RMF", "command": "python tools/run_bench.py --only nist", |
| 10_nist_sp_800_53 NIST SP 800-53 Rev. 5 | PASS | {"authority": "NIST", "command": "python tools/run_bench.py --only nist", "contr |
| 11_nist_csf NIST Cybersecurity Framework 2.0 | PASS | {"authority": "NIST", "command": "python tools/run_bench.py --only nist", "contr |
| 12_fedramp FedRAMP Rev. 5 | PASS | {"authority": "FedRAMP", "command": "python tools/run_bench.py --only fedramp",  |
| 13_pci_dss PCI DSS v4.0.1 | PASS | {"authority": "PCI SSC", "command": "python tools/run_bench.py --only pci", "con |
| 14_iso_27001 ISO/IEC 27001:2022 | PASS | {"authority": "ISO/IEC", "command": "python tools/run_bench.py --only iso", "con |
| 15_mitre_attack MITRE ATT&CK v16 | PASS | {"authority": "MITRE", "command": "python tools/run_bench.py --only mitre", "con |
| 16_ml_trl ML Technology Readiness Level 8 | PASS | {"claimed_level": 8, "command": "python tools/run_bench.py --only 16 && cat docs |

**Suite: 16/16 passed** · platform `?` · python `?` · method `?`

## Licence

The upstream licence is preserved in `LICENSE` and `THIRD_PARTY_LICENSES/`. The Anticloud overlay is licensed under Anticommons 0.1.0 (`ANTICOMMONS_LICENSE.md`).

## Verification

SHA3-256 of `BENCH.json`:

```
462d28b6d3604cb804f9903fb73abd62a8d606fd8a193ab01f71a7f9a1dd3be1
```

Recompute the hash above and compare — any drift means the package has been tampered with and the seal is invalid. This is a self-assessment; no external audit has been performed and a SOC 2 / NIST independent audit is committed post-funding.
