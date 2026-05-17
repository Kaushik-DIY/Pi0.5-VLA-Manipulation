# Kaggle Setup Notes

This project is designed to run in a Kaggle notebook with GPU acceleration.

## Kaggle Runtime Requirements

Before running the notebook, enable:

- Accelerator: GPU
- Internet: On

The project was tested using a Kaggle Tesla T4 GPU.

## Hugging Face Authentication

The Pi0.5 policy depends on gated Hugging Face access through:

- `google/paligemma-3b-pt-224`

Before running the notebook:

1. Open the Hugging Face model page for `google/paligemma-3b-pt-224`.
2. Request or accept access using your Hugging Face account.
3. Create a Hugging Face read token.
4. In Kaggle, open `Add-ons -> Secrets`.
5. Add a secret named `HF_TOKEN`.
6. Store your Hugging Face token as the value.


## Notebook Execution Flow

The notebook performs the following steps:

1. Installs required system packages.
2. Creates a Python 3.12 Miniforge environment.
3. Installs LeRobot, LIBERO, MuJoCo/robosuite, and Pi0.5 dependencies.
4. Authenticates Hugging Face access through Kaggle Secrets.
5. Lists supported LIBERO natural-language task commands.
6. Maps the user-provided instruction to the correct LIBERO task.
7. Runs the Pi0.5 LIBERO-finetuned policy.
8. Saves the generated rollout video.

## Final Successful Task (example)

- Policy: `lerobot/pi05_libero_finetuned`
- Suite: `libero_object`
- Task ID: `7`
- Instruction: `pick up the milk and place it in the basket`

## Scope

This project does not train Pi0.5 from scratch. It integrates and evaluates a pretrained/fine-tuned VLA policy through a terminal-driven simulation pipeline.
