# Reinforcement Learning

## OpenAI Gym Environments
### Creating the environments

To create the environment use the following code snippet:

```
import gym
import deeprl_hw1.envs

env = gym.make('Deterministic-4x4-FrozenLake-v0')
```

### Actions

There are four actions: LEFT, UP, DOWN, RIGHT represented as
integers. The `deep_rl_hw1.envs` contains variables to reference
these. For example:

```
print(deeprl_hw1.envs.LEFT)
```

will print out the number 0.

### Environment Attributes

This class contains the following important attributes:

- `nS` :: number of states
- `nA` :: number of actions
- `P` :: transitions, rewards, terminals

The `P` attribute will be the most important for your implementation
of value iteration and policy iteration. This attribute contains the
model for the particular map instance. It is a dictionary of
dictionary of lists with the following form:

```
P[s][a] = [(prob, nextstate, reward, is_terminal), ...]
```

For example, to get the probability of taking action LEFT in state 0
you would use the following code:

```
env.P[0][deeprl_hw1.envs.LEFT]
```

This would return the list: `[(1.0, 0, 0.0, False)]` for the
`Deterministic-4x4-FrozenLake-v0` domain. There is one tuple in the
list, so there is only one possible next state. The next state will be
state 0, according to the second number in the tuple. This will be the
next state 100\% of the time according to the first number in the
tuple. The reward function for this state action pair `R(0,LEFT) = 0`
according to the third number. The final tuple value says that the
next state is not terminal.

##
### Running a random policy

example.py has an example of how to run a random policy on the domain.

#Value Iteration
The optimal policies for the different environments is in the <environment>.py files.
