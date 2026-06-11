# Bias-in-SHAP-Values

SHAP is widely used to support knowledge-based reasoning about black-box models, but in imbalanced learning settings, explanation results can be misleading. Besides, different machine learning model families may exhibit varying degrees of predictive multiplicity on the same target dataset, i.e., similar predictive accuracy and divergent interpretations. SHAP explainers (TreeSHAP, DeepSHAP, LinearSHAP) differ in their sensitivity to the background data. Particularly, perturbation-based explainers introduce an intrinsic variability in the analysis which directly impacts feature attributions.

We investigate these coupled effects using five binary datasets and four model families (Random Forest, XGBoost, MLP, polynomial logistic regression) across repeated resamples and artificially induced imbalance ratios, to empirically analyse changes in SHAP distributions and feature-rank stability.

To disentangle variability due to model shifts from that introduced by the explainer or background, we introduce model-specific stability indicators: a Predictive Complexity Score for tree ensembles and parameter-variance measures for MLP and polynomial models.
Our results show that severe imbalance amplifies model instability and predictive multiplicity, causing SHAP summaries to fluctuate to the extent that averaging across runs or changing backgrounds becomes unreliable.
We conclude with a practical protocol for using SHAP to extract more stable, actionable knowledge under imbalance.