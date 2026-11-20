### William Chuang

Founder of [Logarchéon Inc.](https://logarcheon.com), an independent research lab.
I fix bugs in systems software and back each fix with a reproducer and machine-checked evidence (Lean, Coq, CBMC, KUnit, fuzzing).
Mathematician by training (M.S./M.A. in Mathematics) · [Google Scholar](https://scholar.google.com/citations?user=ZxTlNB8AAAAJ&hl=en) · [ORCID](https://orcid.org/0009-0008-0796-9478)

#### Upstream work

5 projects · 9 contributions · 1 applied, 3 reviewed

| Project | Contributions | Status |
|---|---|---|
| **Linux kernel** | 5 patches across three filesystems:<br>• GFS2: NULL-pointer fix in the seek path (`gfs2_glock_dq`)<br>• ext4: reject a non-regular boot loader inode in `EXT4_IOC_SWAP_BOOT`<br>• ext4: journal credit shortfalls (swap-boot, inline data), 2 patches<br>• squashfs: error code on the directory header check in lookup | GFS2: [applied by the maintainer](https://lore.kernel.org/all/20261116180002.44336-1-founder@logarcheon.com/T/)<br>ext4: Reviewed-by Jan Kara (SUSE) on [all three](https://lore.kernel.org/all/z4f3glvy73z45sm5pzj27id7hlgio7qyjsdft6gmlahd32y2pg@vbig6wh7rwyb/) ([series](https://lore.kernel.org/all/20261117052750.2955-1-founder@logarcheon.com/)) · awaiting the ext4 maintainer<br>squashfs: [in review](https://lore.kernel.org/all/20261116233530.47177-1-founder@logarcheon.com/) |
| **Ghidra** (NSA) | Decompiler: ARM Thumb locals allocated by `push` ([#9728](https://github.com/NationalSecurityAgency/ghidra/issues/9728)) | [PR #10235 in triage](https://github.com/NationalSecurityAgency/ghidra/pull/10235) |
| **ScubaGear** (CISA) | Entra policies MS.AAD.7.1–7.3 merged admin accounts that share a display name, so 9 Global Admins passed the "at most 8" rule; now counted by object ID ([#2541](https://github.com/cisagov/ScubaGear/issues/2541)) | [PR #2595 open](https://github.com/cisagov/ScubaGear/pull/2595) |
| **TensorFlow Probability** (Google) | Upper-tail survival functions of Chi2, Gamma, Beta and Binomial computed without `1 − cdf`, which rounded to 0 ([#2040](https://github.com/tensorflow/probability/issues/2040)) | [PR #2043 open](https://github.com/tensorflow/probability/pull/2043) |
| **TRIBE v2** (Meta FAIR) | Fix grouped-metric crash in `average_subjects` mode ([#78](https://github.com/facebookresearch/tribev2/issues/78)) | [PR #84 open](https://github.com/facebookresearch/tribev2/pull/84) |

Root-cause analyses, verification artifacts and reproduction scripts: [linux-kernel-contributions](https://github.com/williamchuang/linux-kernel-contributions) (kernel) · [open-source-contributions](https://github.com/williamchuang/open-source-contributions) (other projects).
