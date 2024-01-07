
# Features
- Clean label backdoor attack
- Low poison rate (can be less than 0.05\%)
- All-to-one attack
- Only require target class data
- Physical world attack
- Work with the case that models are trained from scratch

# Requirements
+ Python >= 3.6
+ PyTorch >= 1.10.1
+ TorchVisison >= 0.11.2
+ OpenCV >= 4.5.3

# Usage & HOW-TO
<p align="justify">Use the Narcissus.ipynb notebook for a quick start of our NARCISSUS backdoor attack. The default attack and defense state both use Resnet-18 as the model, CIFAR-10 as the target dataset, and the default attack poisoning rate is 0.5% In-class/0.05% overall.</p>

There are a several of optional arguments in the ```Narcissus.ipynb```:

- ```lab```: The index of the target label
- ```l_inf_r``` : Radius of the L-inf ball which constraint the attack stealthiness.
- ```surrogate_model```, ```generating_model``` : Define the model used to generate the trigger.
- ```surrogate_epochs``` : The number of epochs for surrogate model training.
- ```warmup_round``` : The number of epochs for poi-warm-up trainging.
- ```gen_round``` : The number of epoches for poison generation.
- ```patch_mode``` : Users can change this parameter to ```change```, entering the patch trigger mode. 

## Overall Workflow:
![Narcissus](https://user-images.githubusercontent.com/64983135/162639447-05d02a49-9668-49a0-8d91-c82b952a801e.png)
<p align="justify">The workflow of the Narcissus attack consists of four functional parts (<a href="https://www.cs.columbia.edu/CAVE/databases/pubfig/">PubFig</a> as an example):</p>

- <p align="justify">Step 1: Poi-warm-up: acquiring a surrogate model from a POOD-data-pre-trained model with only access to the target class samples.</p> 
- <p align="justify">Step 2: Trigger-Generation: deploying the surrogate model after the poi-warm-up as a feature extractor to synthesize the inward-pointing noise based on the target class samples;</p> 
- <p align="justify">Step 3: Trigger Insertion: utilizing the Narcissus trigger and poisoning a small amount of the target class sample;</p> 
- <p align="justify">Step 4: Test Query Manipulation: magnifying the Narcissus trigger and manipulating the test results.</p>



# Special thanks to...
[![Stargazers repo roster for @ruoxi-jia-group/Narcissus](https://reporoster.com/stars/ruoxi-jia-group/Narcissus)](https://github.com/ruoxi-jia-group/Narcissus/stargazers)

[![Forkers repo roster for @ruoxi-jia-group/Narcissus](https://reporoster.com/forks/ruoxi-jia-group/Narcissus)](https://github.com/ruoxi-jia-group/Narcissus/network/members)
