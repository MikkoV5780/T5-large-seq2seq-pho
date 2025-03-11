# T5-large-seq2seq-pho

## PhosphoT5: Enhanced T5-Large for Phosphorylation Site Prediction

### Overview
This repository contains an improved version of the T5-large model adapted for the sequence-to-sequence task of predicting protein phosphorylation sites. The model has been enhanced with custom modifications to better handle the transition from annotated to non-annotated protein sequences for accurate phosphorylation site prediction.

### Key Features
* **Specialized Seq2Seq Architecture**: Optimized T5-large model for transforming protein sequences with annotated features to sequences with predicted phosphorylation sites
* **Custom Modifications**: Implemented specific architectural changes to improve prediction accuracy for post-translational modifications
* **Phosphorylation Focus**: Specifically designed to identify potential phosphorylation sites in protein sequences
* **Performance Improvements**: Significant enhancements over baseline T5 models for this specialized bioinformatics task

### Model Architecture
The model builds upon the powerful T5-large architecture and introduces:
* Modified attention mechanisms for better sequence feature recognition
* Customized tokenization approach for protein sequences
* Task-specific fine-tuning methodology for phosphorylation site prediction

### Technical Improvements
* **Focal Loss with Label Smoothing**: Custom `FocalLossWithSmoothing` loss function focuses on difficult examples while preventing overfitting (smoothing=0.035)
* **Noisy Embeddings**: `NoisyT5` wrapper adds Gaussian noise (noise_std=0.1) to input embeddings for better regularization and robustness
* **Training Optimizations**: Gradient accumulation, mixed precision training, dynamic batch sizing, and cross-validation
* **Custom Peptide Tokenizer**: Specialized `RegularTokenizer` tailored for amino acid sequences and peptide-specific notation
* **Advanced Learning Schedule**: Warmup phase with linear decay and early stopping mechanism (patience=3)
* **Multi-iteration Noise Training**: Multiple noise iterations per batch (noise_iterations=2) increase training data diversity
