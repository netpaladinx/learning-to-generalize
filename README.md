# learning-to-generalize

Learning to actively select examples for training and test

## Basic Idea

The ability of generalization is measured by evaluating how well a machine learning
model learned on training data can work on test data. Athough our ultimate goal is
to increase the generalization of our models, we rarely optimize our models
for this objective directly. Instead, what we do conventionally is to fit
the training data by minimizing some loss and treat generalization by some
inferior and coarse techniques, such as adding a norm penalty, and using early
stop. Here, we propse a model that aims to learn the generalization directly 
by actively selecting examples for training and test. Our learning framework is
based on reinforcement learning, and use one cutting-edge deep model - ResNet
to play as the underlying machine learning model.

## Model

### RL Schema 1

- Epoch: one vs multiple
- Actions: Pass, Train, Test
- Reward:
  - Learning effort: - log( #learned-examples + 1 )
  - Learning outcomes:
    - Correct: +1
    - Wrong: -1
  - Bored: -0.1
