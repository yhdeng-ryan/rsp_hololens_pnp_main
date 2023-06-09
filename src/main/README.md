# Main Package

## Contents
### main_node 
- Provides a main entry for executing the project.
- State machine: 
    1. VOID: Determine if the user want to skip registration process.
    2. REGISTRATION: Launch a registration client to start registration process. Go to IDLE if success, ERROR if failed.
    3. IDLE: Wait for user to input the pick and place position markers. Go to PNP if both positions are sent.
    4. PNP: Launch a pnp client to start pick and place. Go to IDLE if success, ERROR if failed.
    5. ERROR: Output error messages.

### hololens_sub
- Subscribes to hololens messages.

### gripper_pub
- Publishes gripper command to robotiq_2f_driver to control the gripper.

### reg_cfg.json
- It sepecified the poses for the registration process.

### main.launch.xml
- This launch file launches every nodes needed for this project to run.

## Usage
### Launch whole project
```
source install/setup.bash
ros2 launch main main.launch.xml
```

### Run the main node individually
```
source install/setup.bash
ros2 run main main_node
```

