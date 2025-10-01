# BLP Code Generation Task

This repository contains resources and scripts for fine-tuning and evaluating models for code generation tasks. The workspace is organized into several directories and files, each serving a specific purpose in the workflow.

## Directory Structure

### `blp-rsft-out/`
This directory contains outputs and configurations related to fine-tuned models.

- **`best-rsft/`**: Contains the best fine-tuned model and its associated files:
  - `adapter_config.json`: Configuration for the adapter model.
  - `adapter_model.safetensors`: Serialized weights of the adapter model.
  - `added_tokens.json`: Additional tokens used during training.
  - `chat_template.jinja`: Template for chat-based interactions.
  - `special_tokens_map.json`: Mapping of special tokens.
  - `tokenizer_config.json`: Configuration for the tokenizer.
  - `tokenizer.json`: Tokenizer data.
  - `tokenizer.model`: Tokenizer model file.
  - `training_args.bin`: Training arguments used for fine-tuning.

- **`blp-sft-dpo/rsft-lora/`**: Contains LoRA fine-tuning configurations and outputs.

### `rsft_ds.hf/`
This directory contains the dataset in Hugging Face's Arrow format:
- `data-00000-of-00001.arrow`: Serialized dataset.
- `dataset_info.json`: Metadata about the dataset.
- `state.json`: Dataset state information.

### Other Files
- `rsft_ds.csv`: Dataset in CSV format.
- `rsft_ds.jsonl`: Dataset in JSON Lines format.
- `blp-task-2.ipynb`: Jupyter notebook for running experiments and evaluations.
- `scoring_v2.py`: Script for scoring or evaluating model outputs.
- `submission.json`: JSON file for submission of results.
- `test_v1.csv`, `trial.csv`, `dev_v2.csv`: CSV files for testing, trial runs, and development data.

## Usage

### Fine-Tuning
The fine-tuning process is managed using the configurations and datasets provided in the `blp-rsft-out/` directory. Use the `adapter_config.json` and `training_args.bin` files to replicate the training setup.

### Evaluation
The `blp-task-2.ipynb` notebook contains code for evaluating the fine-tuned models. Ensure that the required dependencies are installed before running the notebook.

### Scoring
Use the `scoring_v2.py` script to score the model outputs against the test datasets.

## Dependencies
- Python 3.x
- Hugging Face Transformers
- Jupyter Notebook
- Additional dependencies as specified in the notebook or scripts.

## Notes
- The `README.md` files in subdirectories provide additional details about their contents.
- Ensure that the environment variable `TOKENIZERS_PARALLELISM` is set to `false` to avoid parallelism issues during tokenization.

## License
This project is licensed under the MIT License. See the `LICENSE` file for details.