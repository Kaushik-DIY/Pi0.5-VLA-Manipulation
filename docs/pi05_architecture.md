# Pi0.5 Architecture Notes

This project uses `lerobot/pi05_libero_finetuned`, a LIBERO-finetuned Vision-Language-Action policy available through LeRobot.

Pi0.5 is used as the policy model for simulated robotic manipulation. It receives multimodal inputs from the environment, including visual observations, robot state information, and a natural-language task instruction. The model predicts robot actions that are executed in the LIBERO MuJoCo/robosuite simulation.

## Role in This Project

The project does not train Pi0.5 from scratch. Instead, it uses the pretrained/fine-tuned checkpoint for inference.

The main engineering focus is:

- loading the Pi0.5 policy through LeRobot,
- exposing supported LIBERO commands through a terminal-driven interface,
- mapping a natural-language instruction to the correct LIBERO task,
- executing the rollout in simulation,
- saving the resulting robot behavior as a video.

## Final Policy

```text
lerobot/pi05_libero_finetuned
