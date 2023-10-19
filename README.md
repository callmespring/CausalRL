# Dynamic Causal Effects Evaluation in A/B Testing with a Reinforcement Learning Framework (CausalRL)

This repository contains the implementation for the paper ["Dynamic Causal Effects Evaluation in A/B Testing with a Reinforcement Learning Framework"](https://arxiv.org/pdf/2002.01711.pdf) in Python. 

## Summary of the paper

A/B testing, or online experiment is a standard  business strategy to compare a new product with an old one in pharmaceutical, technological, and traditional industries.  Major challenges arise in online experiments of two-sided marketplace platforms (e.g., Uber) 
where there is only one unit that receives a sequence of treatments over time. In those  experiments, the treatment at a given time   impacts  current outcome as well as future outcomes. The aim of this paper is to  introduce a reinforcement learning framework for carrying A/B testing in these experiments, while characterizing the long-term treatment effects. Our proposed testing procedure allows for sequential monitoring and online updating. It is generally applicable to a variety of treatment designs in different industries. In addition, we systematically investigate the theoretical properties (e.g., size and power) of our testing procedure. Finally, we apply our framework to both simulated data and a real-world data example obtained  from a technological company to illustrate its advantage over the current practice. 

<img align="center" src="MDP.png" alt="drawing" width="700">

**Figure 1**: Causal diagram for MDP under settings where treatments depend on current states only. Solid lines represent causal relationships. 

<p float="left">
<img src="4_alpha_1.png" alt="drawing" width="270"> 
<img src="t_alpha_1.png" alt="drawing" width="270">
<img src="BF.png" alt="drawing" width="270">
</p>

**Figure 2**: Empirical rejection probabilities of our test (left), the two-sample t-test (middle) and the modified version of the O'Brien \& Fleming sequential test (right). Settings correspond to the alternating-time-interval, adaptive and Markov design, from top plots to bottom plots.


## File Overview
- `src/`: This folder contains all python codes used in numerical experiments.
  - `conf.py` sets true parameters and functions used in estimation for one experiment.
  We use `<verison>` as the key of a python dict to represent one numerical experiment.
  - `main.py` is an entrance to be used in command line.
  We can type `python main.py <version> 0` to start a new experiment and type
  `python main.py <verison> 1` to see the result if the experiment has executed.
  - `_analyzer.py` contains the functions to make tables and draw plots.
  - `_monitor.py` is a platform to **realize the algorithm in our paper**, which includes the estimation part and hypothesis test part. 
- `data/`: This folder contains raw results and corresponding pics of each experiment.
  - Raw results names are like `<version>.json`.
  - Plots names are like `<version>_<parameter_used_in_estimation>.png`.
  



## Citation

Please cite our paper
["Dynamic Causal Effects Evaluation in A/B Testing with a Reinforcement Learning Framework"](https://arxiv.org/pdf/2002.01711.pdf)

``` 
@article{shi2023dynamic,
  title={Dynamic causal effects evaluation in a/b testing with a reinforcement learning framework},
  author={Shi, Chengchun and Wang, Xiaoyu and Luo, Shikai and Zhu, Hongtu and Ye, Jieping and Song, Rui},
  journal={Journal of the American Statistical Association},
  pages={2059-2071},
  volume={108},
  number={543},
  year={2023},
  publisher={Taylor \& Francis}
}
``` 
