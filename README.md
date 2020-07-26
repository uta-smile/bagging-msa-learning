# Bagging MSA Learning
## Bagging MSA Learning: Enhancing Low-Quality PSSM with Deep Learning for Accurate Protein Structure Property Prediction
https://www.springerprofessional.de/en/bagging-msa-learning-enhancing-low-quality-pssm-with-deep-learni/17911772 RECOMB 2020

Accurate predictions of protein structure properties, e.g. secondary structure and solvent accessibility, are essential in analyzing the structure and function of a protein. PSSM (Position-Specific Scoring Matrix) features are widely used in the structure property prediction. However, some proteins may have low-quality PSSM features due to insufficient homologous sequences, leading to limited prediction accuracy. To address this limitation, we propose an enhancing scheme for PSSM features. We introduce the “Bagging MSA” method to calculate PSSM features used to train our model, and adopt a convolutional network to capture local context features and bidirectional-LSTM for long-term dependencies, and integrate them under an unsupervised framework. Structure property prediction models are then built upon such enhanced PSSM features for more accurate predictions. Empirical evaluation of CB513, CASP11, and CASP12 datasets indicate that our unsupervised enhancing scheme indeed generates more informative PSSM features for structure property prediction.

## Requirements:
cuda 10.2

python 3.6.3

pytorch 1.4.0

smile `pip install smile`

## Unsupervised model training example
```
python -u train.py --aln_dpath='./aln_example' --train_fname='sample.aln' --valid_fname='sample.aln' --model_path=./try01 2>&1 | tee try01.log
```
See comments for all hyper-parameters in `train.py`

See `./aln_example/sample.aln` for an example of input MSA file.

## Generate enhanced feature
```
python -u generate_new_feat.py --eval_feat_path='./feat_example/sample2.feat' --save_fpath='./feat_example/new.feat' --model_path='./try01' --epoch=1
```
See comments for all hyper-parameters in `generate_new_feat.py`

See `./feat_example/sample2.feat` for an example of input feat file.


## Citation:
Please cite the following paper in your publication if it helps your research:

Guo, Y., Wu, J., Ma, H., Wang, S. and Huang, J., 2020, May. Bagging MSA Learning: Enhancing Low-Quality PSSM with Deep Learning for Accurate Protein Structure Property Prediction. In International Conference on Research in Computational Molecular Biology (pp. 88-103). Springer, Cham.
