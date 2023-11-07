# Generalized Weighted Path Consistency for Mastering Atari Games

This is open-source codebase for GW-PCZero, from "Generalized Weighted Path Consistency for Mastering Atari Games" at NeurIPS2023. You can find our poster 

[here]:https://github.com/CMACH508/GW_PCZero/picture/poster.png to get a quick overview of our work.

## Description
Path consistency (PC) is defined as "*f values on one optimal path should
be identical*". PCZero realised the PC constraint for the first time, demonstrating the effectiveness of PC. However, there still exist deficiencies for PCZero:
1. Only board games, wherein the immediate reward is always zero until the game 
terminates, are considered.
2. Unreliable nodes in the collected path were not filtered out.
3. Lack strong theoretical foundation to support the effectiveness of PC.

This paper generalize the early PCZero into GW-PCZero from three new developments:
1. Generalize the application of PC from board games to scenarios where the 
environment emits immediate rewards, such as Atari games.
2. An uncertainty-aware weighting mechanism is introduced for accurate 
computation of the PC target.
3. This paper establishes a theoretical foundation for PC. We prove that neuralguided MCTS is guaranteed to find the optimal solution for the first time, under 
the constraint of PC.

## Training and Testing
We provide train.sh and test.sh for training and evaluation. The training process is the same as EfficientZero.

## Requirements

Our GW_PCZero is built on EfficientZero, which requires python3 (>=3.6) and pytorch (>=1.8.0) with the development headers.
Before starting training, you need to build the c++/cython style external packages. (GCC version 7.5+ is required.)

```
cd core/ctree
bash make.sh
```
As for other packages required for this codebase, please run 
```
pip install -r requirements.txt
```

## Citation

If you find this repo useful, please cite our paper:

```
@inproceedings{zhao2023generalized,
  title={Generalized Weighted Path Consistency for Mastering Atari Games},
  author={Dengwei Zhao, and Shikui Tu, and Lei Xu},
  booktitle={NeurIPS},
  year={2023}
}
```

## Contact

If you have any question or want to use the code, please contact <zdwccc@sjtu.edu.cn>

## Acknowledgement

We appreciate the following github repos greatly for their valuable code base implementations:
<https://github.com/YeWR/EfficientZero>

<https://github.com/koulanurag/muzero-pytorch>