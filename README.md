**Multi-UAV Partial Observation Environment**
This repository provides a custom Multi-UAV (Unmanned Aerial Vehicle) simulation environment built using OpenAI Gymnasium. The environment is designed for reinforcement learning experiments involving partial observability, adversarial agents, sensor noise/dropout, and obstacle avoidance in a 3D grid space.
The model incorporates obstacle avoidance along with different adveserial scenarios. 

**Features**
1. Multiple cooperative UAVs.
2. Partial observations with GPS, LIDAR, battery and signal inputs
3. Configurable adversarial behavior and sensor dropout
4. Obstacle detection and navigation
5. Continuous action and observation spaces
6. Suitable for training multi-agent reinforcement learning(MARL) policies

**Dependencies**
1. Gymnasium
2. Numpy
3. Unity (for environment modelling and testing)

**Observation Space**
Each of the UAV receives the following obsrevations: 
1. GPS coordinates(x,y,z). The z coordinate is made constant for simplicity making the model essentially a 2D model. The z coordinate is kept to be smaller than that of height of the obstacles, so that the each of the UAV can find optimal path using RL and do not just fly over all of them. 
2. LIDAR readings(3 values)
3. Battery Levels
4. Signal strength
5. Relative positions of nearby obstacles: 2 x number of obstacles

**Action Space**
Each UAV takes a 3D thrust vector (x,y,z) in a continuous range [-1.0,1.0]. 

**Configuration Parameters**
1. grid_size-Size of 3D(essentially 2D) environment
2. max_steps- Maximum steps per episode
3. adversarial-Enable adversarial agents
4. sensor_dropout- Enable/disable random sensor failures
5. num_obstacles- Number of static obstacles
6. num_uavs-Number of UAV agents

**Use Cases**
1. Multi-agent path planning
2. Robust RL Under partial observability
3. Exploration of adversarial and cooperative dynamics
4. Sensor fusion and fault-tolerant navigation
