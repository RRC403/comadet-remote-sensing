# CoMADet Remote Sensing

Contribution modules for CoMADet, Mining and Arbitrating Similar-Category Confusion for Small Object Detection in UAV and Remote Sensing Imagery.

This repository contains the method-specific code used by the paper. The complete contribution-module release is provided as CoMADet-contribution-modules.zip. The archive also contains the reproducibility configuration snapshots and split-generation inputs under reproducibility. It does not include the full MMRotate framework, datasets, checkpoints, prediction caches, training logs, or generated results. Extract the archive and use the files under src with the upstream MMRotate and MMEngine/MMCV dependencies.

## Included components

- Confusion Matrix Mining and multi-pair Similar Category Angle supervision in src/mmrotate/models/losses/msca_loss.py and the CMM head adapter.
- Cross-Scale Instance Contrast and its stable training path in the contrastive head modules.
- Class-prototype discrimination in the CPD modules, including the combined contrastive and prototype head.
- The CoMADet-L lightweight LSE-FPN neck and structural reparameterization helpers.
- Confusion-mined arbitration post-processing in cma, including pair-class reclassification, multi-view caching, and score arbitration.

## Integration

After extracting the release archive, the files under src/mmrotate mirror the corresponding paths in a compatible MMRotate checkout. Copy them into the matching paths of the framework checkout, then register the new classes through the framework's normal registry imports. The cma scripts expect detector outputs and dataset metadata in the formats described in their module docstrings.

The archive includes the configuration snapshots and split-generation inputs used for the reported experiments. The original third-party datasets, generated patch images, checkpoints, prediction caches, and training logs are not redistributed.

## Reproducibility notes

- Do not commit datasets, model checkpoints, prediction caches, or generated result files.
- Set dataset roots and checkpoint paths locally.
- Review the configuration and class-pair settings before running on a dataset.
- The code is released as the research implementation associated with the paper and may require the matching MMRotate revision.

## Citation

If you use these modules, please cite the associated CoMADet paper after publication.
