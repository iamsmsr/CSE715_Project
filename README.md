# CSE715_Project
In this project, you will implement an unsupervised learning pipeline inspired by Varia- tional Autoencoders (VAE) for clustering hybrid language music tracks. The goal is to  extract latent representations from audio and/or lyrics and perform clustering. Different VAE architectures, analyze clustering and  compare with baseline methods .


We systematically implement VAE architectures for unsupervised clustering: Task 1
(text-only VAE on song lyrics), Task 2 (Conv-VAE on Common Voice paired audio-text,
12K samples), Task 3 (Beta-CVAE on GTZAN music with genre conditioning, 1K tracks).
Key finding: NMI ≈ 0.01 − 0.02 across all methods. Critical insight from Task 2: even
with properly paired audio-text, multi-modal fusion degrades clustering by 55% (Silhouette
0.0725 → 0.0326), revealing fundamental conflicts between acoustic and semantic feature
spaces. Task 3 ablation (6 configs) demonstrates that increasing KL weight β (for disentan-
glement) destroys genre discriminability (NMI: 0.0175 → 0.0020 → collapse). Beta-CVAE
achieves Silhouette=0.9910 but Purity=0.1090 (40% worse than simple PCA), proving inter-
nal compactness masks lack of discriminability. Conclusion: unsupervised clustering failure
stems from data characteristics and fundamental task-model conflicts, not architectural de-
ficiencies. Multi-modal fusion alone is insufficient; supervised approaches required.
Keywords: Variational Autoencoders, Audio-Text Fusion, Unsupervised Clustering,
Multi-Modal Learning, Disentanglement Trade-off
