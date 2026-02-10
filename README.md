# SpaCE-Eval: A Benchmark for Real-World Multi-Modal Reasoning

Welcome to the official codebase of SpaCE-Eval! 

The [paper](https://openreview.net/forum?id=VAEkLS9VBr&noteId=QSQY2kkQHy) is accepted to ICLR 2026.


Dataset can be downloaded at:
https://huggingface.co/datasets/XuyouYang/SpaCE-Eval
## About the Benchmark

This benchmark provides a comprehensive evaluation of MLLMs across the following categories:
- Spatial Reasoning
- Commonsense Knowledge
- Environment Interaction

The dataset consists of newly created diagrams with image-question pairs, carefully curated through a standardized annotation and filtering pipeline.

## Quick Start

### Setup

Most models are evaluated using the [OpenRouter API](https://openrouter.ai/) for efficiency. For models not supported by OpenRouter, we use [VLLM](https://github.com/vllm-project/vllm) with default inference hyperparameters.

To install required dependencies:

```bash
pip install -r requirements.txt
```

### Evaluation

To access the dataset, please clone the following temporary anonymous repository:

```shell
cd ./data
git clone https://huggingface.co/datasets/XuyouYang/SpaCE-Eval
```

To evaluate different models on the benchmark:

```shell
# test by openrouter api, generate the result in a JSON file. 
python eval.py --model all # test all the models
python eval.py --model gpt-4o # test one model
```

To calculate accuracy from result files:

```python
python calc_acc.py --jsons gpt-4o_open_router_check.json # gpt-4o accuracy
```
### Citation

```bibtex
@inproceedings{yang2026spaceeval,
  title     = {SpaCE-Eval: A Benchmark for Real-World Multi-Modal Reasoning},
  author    = {Yang, Xuyou and Zhao, Yucheng and Zhang, Wenxuan and Koh, Immanuel},
  booktitle = {Proceedings of the International Conference on Learning Representations (ICLR)},
  year      = {2026}
}
