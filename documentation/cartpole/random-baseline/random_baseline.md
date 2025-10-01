# SCRUM-15: Researching Cartpole test write

## Environment Details
- Action space: Discrete(2)
- Observation space: Box([-4.8               -inf -0.41887903        -inf], [4.8               inf 0.41887903        inf], (4,), float32)
- Maximum steps per episode: 500

## Observation Meaning
**Observation vector (4 values):**
1. **Cart Position (m)** — horizontal position on the track (≈ -4.8 to +4.8).
2. **Cart Velocity (m/s)** — how fast the cart moves (unbounded float in practice).
3. **Pole Angle (rad)** — tilt of the pole relative to vertical (≈ -0.4189 to +0.4189 rad ≈ ±24°).
4. **Pole Angular Velocity (rad/s)** — how fast the pole is rotating (unbounded float in practice).

## Failure Conditions
**Episode ends when (termination/truncation):**
- **Pole tilt exceeds ±0.4189 rad (~±24°)** → `terminated = True`
- **Cart position leaves track bounds (≈ ±4.8 m)** → `terminated = True`
- **Time limit of 500 steps is reached** → `truncated = True`

## Example Run
- Starting observation: [0.2273874282836914, 1.5554898977279663, -0.24202966690063477, -2.3927321434020996]
- Total reward: 16.0
