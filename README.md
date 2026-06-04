# ColabDesign (MotifCraft fork)

> **Use with [MotifCraft](../README.md).** This directory is not intended as a standalone install. Install it from the MotifCraft repository root via `install_motifcraft.sh`, which runs `pip install ./ColabDesign`. See the [MotifCraft README](../README.md) for the full pipeline, settings, and loss weights.

This is a customised fork of [ColabDesign](https://github.com/sokrypton/ColabDesign) for **motif scaffolding** and **binder design** in MotifCraft. For the upstream project, docs, and Colab notebooks, see the [original repository](https://github.com/sokrypton/ColabDesign).

### MotifCraft-specific changes (AfDesign)

- **`partial` / `partial_binder` protocols** — fix motif backbone and/or sequence while hallucinating connecting loops and scaffold
- **Motif supervision losses** — Cα RMSD to input (`rmsd`), combined motif pAE + RMSD (`motif_combined`, sigmoid scale `rmsd_scale`), motif–scaffold contact loss (`con` / `i_con`)
- **Target cropping** — `crop_indices` / `crop` in the evoformer and structure module to design on a trimmed target (embedding crop); hotspot remapping for cropped coordinates
- **Stage-wise motif weights** — two-step 4stage schedules (e.g. stronger `rmsd` / `motif_combined` in early logits) are driven from `MotifCraft/functions/colabdesign_utils.py`

---

### Making Protein Design accessible to all via Google Colab!
- P(structure | sequence)
  - [TrDesign](/tr) - using TrRosetta for design
  - [AfDesign](/af) - using AlphaFold for design
  - [WIP] [RfDesign](https://github.com/RosettaCommons/RFDesign) - using RoseTTAFold for design
- P(sequence | structure)
  - [ProteinMPNN](/mpnn)
  - [WIP] TrMRF
- P(sequence)
  - [WIP] [MSA_transformer](/esm_msa)
  - [WIP] [SEQ](/seq) - (GREMLIN, mfDCA, arDCA, plmDCA, bmDCA, etc)
- P(structure)
  - [Rfdiffusion](/rf)

### Where can I chat with other ColabDesign users?
  - See our [Discord](https://discord.gg/gna8maru7d) channel!

### Presentations
[Slides](https://docs.google.com/presentation/d/1Zy7lf_LBK0_G3e7YQLSPP5aj_-AR5I131fTsxJrLdg4/)
[Talk](https://www.youtube.com/watch?v=2HmXwlKWMVs)

### Contributors (upstream ColabDesign):
- Sergey Ovchinnikov [@sokrypton](https://github.com/sokrypton)
- Shihao Feng [@JeffSHF](https://github.com/JeffSHF)
- Justas Dauparas [@dauparas](https://github.com/dauparas)
- Weikun.Wu [@guyujun](https://github.com/guyujun) (from [Levinthal.bio](http://levinthal.bio/en/))
- Christopher Frank [@chris-kafka](https://github.com/chris-kafka)
