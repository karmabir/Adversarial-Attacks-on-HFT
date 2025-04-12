# When Milliseconds Matter: Evaluating the Vulnerability of High-Frequency Trading Models to Adversarial Manipulation

## Overview
This research investigates the vulnerability of high-frequency trading (HFT) models to adversarial attacks. As machine learning becomes increasingly integrated into financial systems, particularly in high-frequency trading where decisions are made in microseconds to milliseconds, understanding these vulnerabilities is crucial for market stability and security.

## Research Questions
- How vulnerable are state-of-the-art HFT models to adversarial attacks?
- What is the real-world financial impact of these vulnerabilities?
- Which model architectures demonstrate greater resilience against attacks?

## Dataset
- FI-2010 dataset (introduced in 2017)
- Covers 5 liquid stocks traded on NASDAQ
- 10 consecutive trading days (June 1-14, 2010)
- Over 4 million events (submissions, cancellations, modifications, executions)
- Millisecond precision with 10 levels of depth for bid and ask sides

## Methodology
### Models Tested
- DeepLOB: State-of-the-art hybrid CNN-LSTM architecture for limit order book prediction
- CNN-1: Simple convolutional model with basic feature extraction
- CNN-2: More sophisticated convolutional model with inception-inspired design
- LSTM-1: Stacked LSTM model for temporal dependencies
- LSTM-2: Simpler LSTM model with strong regularization

### Adversarial Attack Methods
- Fast Gradient Sign Method (FGSM): Single-step attack that perturbs input in direction of gradient
- Projected Gradient Descent (PGD): Multi-step iterative variant of FGSM with bounded constraints

### Evaluation Framework
1. Baseline performance measurement (accuracy, precision, recall, AUC)
2. Adversarial attack implementation with HFT-specific constraints
3. Financial impact quantification through simulated trading strategies

## Key Findings
1. **Performance-Vulnerability Trade-off**: Highest-performing models (CNN-2, DeepLOB) showed greatest vulnerability to attacks
2. **Architectural Insights**: CNN-2 outperformed more complex DeepLOB in both profits and attack resilience
3. **Attack Sensitivity Patterns**: 
   - PGD attacks generated worse trading signals in CNN-2 and DeepLOB
   - FGSM attacks were more disruptive to LSTM models
4. **Beneficial Perturbations**: In some cases, perturbations acted as beneficial regularization
5. **Incidental Robustness**: Simpler architectures (CNN-1, LSTM-2) demonstrated "incidental robustness"

## Practical Implications
- HFT firms should consider adversarial robustness alongside performance metrics when deploying models
- Balanced approaches like LSTM-1 offer safer deployment with consistent profitability under attacks
- Attack type sensitivity suggests defensive strategies should be tailored to specific model architectures

## Future Research Directions
1. Further investigate why simpler architectures outperform complex ones in both profit and robustness
2. Develop defense strategies combining adversarial training with model-specific optimizations
3. Explore ensemble approaches combining high-performing models with robust ones

## References
See the full list of references in the presentation.

## Author
Karmabir Chakraborty, Penn State University
Advisor: Dr. Hajime Shimao
