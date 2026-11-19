# Principal Components Lab

An interactive study guide for §20.1, 20.1.1, 20.1.3 and 20.1.4 of Kevin P. Murphy, *Probabilistic Machine Learning: An Introduction*
(principal components analysis as minimum reconstruction error and maximum variance, eigen-images, covariance vs correlation, the Gram-matrix trick for D > N, PCA by exact and randomized SVD, and choosing the number of components).

**Live:** https://isaackrallison.github.io/principal-components-analysis/

Every section has an **Explain it** box at four levels (Kid, High school, Undergrad, Grad / MLE), switchable globally from the top bar.

- **20.1 PCA:** Fig. 20.1 live. Turn the projection line by dragging or with a slider and watch the residuals, reconstructions and 1-D codes. The distortion 𝓛(θ) and projected variance 𝕍[z](θ) always add to tr Σ̂. Includes snap-to-eigenvector, a power-iteration step, and an elongation slider that shows how unstable the first PC gets when λ₁ ≈ λ₂.
- **20.1.1 Examples:** Fig. 20.2 and 20.3 with 300 procedurally drawn 16×16 digit 9s (D = 256). The 2-D PCA scatter has a 5/25/50/75/95% quantile grid and the nearest image to each vertex. Click to decode any (z₁, z₂). The mean and first six eigen-images, sliders to build x̄ + Σ zₖ√λₖ wₖ, and images rebuilt from L = 1–60 numbers.
- **20.1.3.1 Covariance vs correlation:** Fig. 20.5 on simulated heights and weights. Switch units (m/in/cm, kg/lb/oz) and the raw PC1 swings from pure height to pure weight, while the standardized PC1 stays at (1, 1)/√2.
- **20.1.3.2 High-dimensional data:** eigendecompose XᵀX (D×D) or XXᵀ (N×N) with V = XᵀUΛ^(−½) (Eqs. 20.21–20.22). Both routes are timed in the browser and compared eigenvalue by eigenvalue and vector by vector.
- **20.1.3.3 PCA by SVD:** X ≈ U S Vᵀ on the digit matrix, with a randomized SVD (rank L, oversampling p, q power iterations) checked against the exact eigendecomposition (λₖ = sₖ²/N, |cos(vₖ, wₖ)|), storage NL + L + LD and rank-L reconstructions.
- **20.1.4.1–20.1.4.3 Choosing L:** train vs test reconstruction error (Fig. 20.6, with Eq. 20.26 checked numerically), scree plot and fraction of variance explained with τ and Kaiser rules (Fig. 20.7), and the profile likelihood change-point model with μ₁, μ₂, ±σ bands and argmax (Eqs. 20.28–20.31, Fig. 20.8). Runs on the digits or on synthetic data with a known number of factors L* and adjustable noise.
- A 48-question quiz tagged by level and a cheat sheet.

Single self-contained `index.html`, no build step. Loads Google Fonts and MathJax from cdnjs. All data are synthetic and generated in the page from fixed seeds. Every eigendecomposition (Householder tridiagonalization + implicit QL), SVD and randomized SVD is computed live in the browser.
