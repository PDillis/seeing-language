# Learning to See Through Language
Using pre-trained frozen LLMs to learn vision tasks. In this repository, will follow the training of diverse (optimally lightweight) Large Language Models (LLMs) as the self-attention and feedforward layers are kept frozen. Instead, what is trained is the positional and input embeddings, as well as the output layer, should this one have any parameters to train. 

This work is inspired by the paper [Pretrained Transformers As Universal Computation Engines](https://arxiv.org/abs/2103.05247). As such, we will start with replicating their results on smaller vision tasks such as classifying [MNIST](https://yann.lecun.com/exdb/mnist/) and [CIFAR10](https://www.cs.toronto.edu/~kriz/cifar.html), then we can move on to much harder tasks that aren't necessarily classification (such as depth estimation, end-to-end autonomous driving, etc.). This repository was also inspired by the work done by Kevin Lu @kzl in his repository [`universal-computation`](https://github.com/kzl/universal-computation), so check it out for more details and tests on other tasks.

## LLMs
Given that we wish to train these models as quickly as possible, we will focus on using the *smaller* variants of LLMs. We will then proceed to do our experiments using [GPT2](https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf) and more recent models such as [SmolLM2](https://huggingface.co/HuggingFaceTB/SmolLM2-135M). We will first test with the smallest variant of each model and then, based on these results, we will proceed to use larger variants or even larger models, if we see the task at hand hasn't been saturated already.