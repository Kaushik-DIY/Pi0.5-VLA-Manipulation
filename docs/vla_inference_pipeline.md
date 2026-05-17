# VLA Inference Pipeline

The system runs a closed-loop Vision-Language-Action policy execution pipeline.

```text
User enters supported natural-language command
        ↓
Task registry lookup
        ↓
Instruction mapped to LIBERO suite + task ID
        ↓
LIBERO initializes MuJoCo/robosuite scene
        ↓
LeRobot loads Pi0.5 LIBERO-finetuned policy
        ↓
Camera observations + robot state + language task are processed
        ↓
Pi0.5 predicts robot actions
        ↓
Robot executes manipulation in simulation
        ↓
Rollout video is saved
