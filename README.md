# KBGAN
## This repo is the pytorch-v0.4.1 implement version for KBGAN. But the results is not consistent with the original result.

> The origin repo: https://github.com/cai-lw/KBGAN  
> Liwei Cai and William Yang Wang, "KBGAN: Adversarial Learning for Knowledge Graph Embeddings", in *Proceedings of The 16th Annual Conference of the North American Chapter of the Association for Computational Linguistics: Human Language Technologies (NAACL HLT 2018)*.    
> Paper: https://arxiv.org/abs/1711.04071

## Dependencies
* Python 3.6
* PyTorch 0.4.1
* PyYAML
* nvidia-smi


## Usage
* Pretrain(for example):   
python pretrain.py --config=config_fb15k237.yaml --pretrain_config=TransE  
python pretrain.py --config=config_fb15k237.yaml --pretrain_config=DistMult  
(this will generate a pretrained model file)
* Adversarial train:  
 python gan_train.py --config=config_fb15k237.yaml --g_config=TransE --d_config=DistMult  
(make sure that G model and D model are both pretrained)   
***
Feel free to explore and modify parameters in config files. Default parameters are those used in experiments reported in the paper.  
Decrease **test_batch_size** in config files if you experience GPU memory exhaustion. (this would make the program runs slower, but would not affect the test result)
