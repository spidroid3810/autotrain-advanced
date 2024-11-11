# 🤗 AutoTrain Advanced

AutoTrain Advanced: faster and easier training and deployments of state-of-the-art machine learning models. AutoTrain Advanced is a no-code solution that allows you to train machine learning models in just a few clicks. Please note that you must upload data in correct format for project to be created. For help regarding proper data format and pricing, check out the documentation. 

NOTE: AutoTrain is free! You only pay for the resources you use in case you decide to run AutoTrain on Hugging Face Spaces. When running locally, you only pay for the resources you use on your own infrastructure.

## Supported Tasks

| Task | Status | Python Notebook | Example Configs |
| --- | --- | --- | --- |
| LLM SFT Finetuning | ✅ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/huggingface/autotrain-advanced/blob/main/notebooks/llm_finetuning.ipynb) | [llm_sft_finetune.yaml](https://github.com/huggingface/autotrain-advanced/blob/main/configs/llm_finetuning/smollm2.yml) |
| LLM ORPO Finetuning | ✅ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/huggingface/autotrain-advanced/blob/main/notebooks/llm_finetuning.ipynb) | [llm_orpo_finetune.yaml](https://github.com/huggingface/autotrain-advanced/blob/main/configs/llm_finetuning/llama3-8b-orpo.yml) |
| LLM DPO Finetuning | ✅ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/huggingface/autotrain-advanced/blob/main/notebooks/llm_finetuning.ipynb) | [llm_dpo_finetune.yaml](https://github.com/huggingface/autotrain-advanced/blob/main/configs/llm_finetuning/llama3-8b-dpo-qlora.yml) |
| LLM Reward Finetuning | ✅ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/huggingface/autotrain-advanced/blob/main/notebooks/llm_finetuning.ipynb) | [llm_reward_finetune.yaml](https://github.com/huggingface/autotrain-advanced/blob/main/configs/llm_finetuning/llama32-1b-sft.yml) |
| LLM Generic/Default Finetuning | ✅ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/huggingface/autotrain-advanced/blob/main/notebooks/llm_finetuning.ipynb) | [llm_generic_finetune.yaml](https://github.com/huggingface/autotrain-advanced/blob/main/configs/llm_finetuning/gpt2_sft.yml) |
| Text Classification | ✅ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/huggingface/autotrain-advanced/blob/main/notebooks/text_classification.ipynb) | [text_classification.yaml](https://github.com/huggingface/autotrain-advanced/tree/main/configs/text_classification) |
| Text Regression | ✅ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/huggingface/autotrain-advanced/blob/main/notebooks/text_regression.ipynb) | [text_regression.yaml](https://github.com/huggingface/autotrain-advanced/tree/main/configs/text_regression) |
| Token Classification | ✅ | Coming Soon | [token_classification.yaml](https://github.com/huggingface/autotrain-advanced/tree/main/configs/token_classification) |
| Seq2Seq | ✅ | Coming Soon | [seq2seq.yaml](https://github.com/huggingface/autotrain-advanced/tree/main/configs/seq2seq) |
| Extractive Question Answering | ✅ | Coming Soon | [extractive_qa.yaml](https://github.com/huggingface/autotrain-advanced/tree/main/configs/extractive_question_answering) |
| Image Classification | ✅ | Coming Soon | [image_classification.yaml](https://github.com/huggingface/autotrain-advanced/tree/main/configs/image_classification) |
| Image Scoring/Regression | ✅ | Coming Soon | [image_regression.yaml](https://github.com/huggingface/autotrain-advanced/tree/main/configs/image_scoring) |
| DreamBooth LoRA | ✅ | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/huggingface/autotrain-advanced/blob/main/colabs/AutoTrain_Dreambooth2.ipynb) | [dreambooth_lora.yaml](https://github.com/huggingface/autotrain-advanced/tree/main/configs/dreambooth) |
| VLM | 🟥 | Coming Soon | [vlm.yaml](https://github.com/huggingface/autotrain-advanced/tree/main/configs/vlm) |


## Running UI on Colab or Hugging Face Spaces

- Deploy AutoTrain on Hugging Face Spaces: [![Deploy on Spaces](https://huggingface.co/datasets/huggingface/badges/resolve/main/deploy-on-spaces-md.svg)](https://huggingface.co/login?next=%2Fspaces%2Fautotrain-projects%2Fautotrain-advanced%3Fduplicate%3Dtrue)


- Run AutoTrain UI on Colab via ngrok: [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/huggingface/autotrain-advanced/blob/main/colabs/AutoTrain_ngrok.ipynb)


## Local Installation

You can Install AutoTrain-Advanced python package via PIP. Please note you will need python >= 3.10 for AutoTrain Advanced to work properly.

    pip install autotrain-advanced
    
Please make sure that you have git lfs installed. Check out the instructions here: https://github.com/git-lfs/git-lfs/wiki/Installation

You also need to install torch, torchaudio and torchvision.

The best way to run autotrain is in a conda environment. You can create a new conda environment with the following command:

    conda create -n autotrain python=3.10
    conda activate autotrain
    pip install autotrain-advanced
    conda install pytorch torchvision torchaudio pytorch-cuda=12.1 -c pytorch -c nvidia
    conda install -c "nvidia/label/cuda-12.1.0" cuda-nvcc

Once done, you can start the application using:

    autotrain app --port 8080 --host 127.0.0.1


If you are not fond of UI, you can use AutoTrain Configs to train using command line or simply AutoTrain CLI.

To use config file for training, you can use the following command:

    autotrain --config <path_to_config_file>


You can find sample config files in the `configs` directory of this repository.

Example config file for finetuning SmolLM2:

```yaml
task: llm-sft
base_model: HuggingFaceTB/SmolLM2-1.7B-Instruct
project_name: autotrain-smollm2-finetune
log: tensorboard
backend: local

data:
  path: HuggingFaceH4/no_robots
  train_split: train
  valid_split: null
  chat_template: tokenizer
  column_mapping:
    text_column: messages

params:
  block_size: 2048
  model_max_length: 4096
  epochs: 2
  batch_size: 1
  lr: 1e-5
  peft: true
  quantization: int4
  target_modules: all-linear
  padding: right
  optimizer: paged_adamw_8bit
  scheduler: linear
  gradient_accumulation: 8
  mixed_precision: bf16
  merge_adapter: true

hub:
  username: ${HF_USERNAME}
  token: ${HF_TOKEN}
  push_to_hub: true
```

To fine-tune a model using the config file above, you can use the following command:

```bash
$ export HF_USERNAME=<your_hugging_face_username>
$ export HF_TOKEN=<your_hugging_face_write_token>
$ autotrain --config <path_to_config_file>
```


## Documentation

Documentation is available at https://hf.co/docs/autotrain/

## Citation

```
@misc{thakur2024autotrainnocodetrainingstateoftheart,
      title={AutoTrain: No-code training for state-of-the-art models}, 
      author={Abhishek Thakur},
      year={2024},
      eprint={2410.15735},
      archivePrefix={arXiv},
      primaryClass={cs.AI},
      url={https://arxiv.org/abs/2410.15735}, 
}
```
