# Color-Invariant Saree Design Recognition — DeepLure AIE-CASE

## Objective
Recognize/verify saree **design identity regardless of colorway**.

## Approach
- ImageNet-pretrained ConvNeXt-Atto backbone
- GeM pooling
- 256-dimensional L2-normalized embeddings
- Synthetic colorway augmentation in CIELAB
- Multi-positive supervised contrastive learning
- Cosine-similarity retrieval
- Verification using ROC-AUC/EER and a validation-calibrated threshold
- Near-duplicate grouping before train/validation/test split to reduce leakage

## How to run
1. Open the notebook in Google Colab.
2. Select a GPU runtime (T4 recommended).
3. Set `DATA_ROOT` to the DeepLure dataset folder supplied for the assessment.
4. Run all cells.
5. Check `final_results.csv`.
6. Submit the notebook/repository link requested by the assessment form.

## Important
The final numerical metrics must come from your actual run. Do not replace them with example or fabricated values.

## Interview explanation
The model learns the **spatial motif/design** instead of relying on color. Synthetic recoloring creates positive examples of the same design in different colorways. Contrastive learning makes those embeddings close while keeping different designs apart. Same-palette impostor tests are included to detect color bias.

## Expected submission files
- `Color_Invariant_Saree_Design_Recognition.ipynb`
- `README.md`
- `final_results.csv` (generated after the notebook is run)
- optionally the trained checkpoint `saree_color_invariant_best.pt` if the form requests it

This implementation is an original compact implementation of the assessment's stated problem; the official assessment dataset and any private DeepLure materials are not redistributed here.
