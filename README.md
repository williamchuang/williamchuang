### William Chuang

Founder of [Logarchéon Inc.](https://logarcheon.com), an independent research lab.
I fix bugs in systems software and back each fix with a reproducer and machine-checked evidence (Lean, Coq, CBMC, KUnit, fuzzing).
Mathematician by training (M.S./M.A. in Mathematics) · [Google Scholar](https://scholar.google.com/citations?user=ZxTlNB8AAAAJ&hl=en) · [ORCID](https://orcid.org/0009-0008-0796-9478)

#### Upstream work

| Project | Change | Status |
|---|---|---|
| Linux kernel · GFS2 | NULL-pointer fix in the seek path (`gfs2_glock_dq`) | [Applied by the maintainer](https://lore.kernel.org/all/20261116180002.44336-1-founder@logarcheon.com/T/) |
| Linux kernel · ext4 | Reject a non-regular boot loader inode in `EXT4_IOC_SWAP_BOOT` | [In review](https://lore.kernel.org/all/20261117061822.3826-1-founder@logarcheon.com/) |
| Linux kernel · ext4 | Journal credit shortfalls (swap-boot, inline data) | [In review](https://lore.kernel.org/all/20261117052750.2955-1-founder@logarcheon.com/) |
| Linux kernel · squashfs | Error code on the directory header check in lookup | [In review](https://lore.kernel.org/all/20261116233530.47177-1-founder@logarcheon.com/) |
| Ghidra (NSA) | Decompiler: ARM Thumb locals allocated by `push` ([#9728](https://github.com/NationalSecurityAgency/ghidra/issues/9728)) | [PR #10235 in triage](https://github.com/NationalSecurityAgency/ghidra/pull/10235) |
| TRIBE v2 (Meta FAIR) | Fix grouped-metric crash in `average_subjects` mode ([#78](https://github.com/facebookresearch/tribev2/issues/78)) | [PR #84 open](https://github.com/facebookresearch/tribev2/pull/84) |
| TensorFlow Probability (Google) | Upper-tail survival functions of Chi2, Gamma, Beta and Binomial computed without `1 − cdf`, which rounded to 0 ([#2040](https://github.com/tensorflow/probability/issues/2040)) | [PR #2043 open](https://github.com/tensorflow/probability/pull/2043) |

Patches, root-cause analyses and verification artifacts for each kernel submission: [linux-kernel-contributions](https://github.com/williamchuang/linux-kernel-contributions).
