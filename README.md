<p align="center">
    <img src="minari-text.png" width="500px"/>
</p>

Minari is the new name of this library. Minari used to be called Kabuki.

Minari is intended to be a Python library for conducting research in offline reinforcement learning, akin to an offline version of Gymnasium or an offline RL version of HuggingFace's datasets library. This library is currently in beta, and we're targeting having a complete initial release in February

We have a public discord server (which we also use to coordinate development work) that you can join here: https://discord.gg/jfERDCSw.


## Installation
`pip install numpy cython`

`pip install git+https://github.com/Farama-Foundation/Minari.git`

## Downloading datasets

```python
import minari

dataset = minari.download_dataset("LunarLander_v2_remote-test-dataset")
```

## Recreating Gymnasium environments (Coming very soon!)

```python
import json
import gymnasium as gym
from gymnasium.utils.serialize_spec_stack import deserialise_spec_stack

env = gym.make(deserialise_spec_stack(json.loads(dataset.environment_stack)))
```

## Uploading datasets

```python
dataset.save()
dataset = minari.upload_dataset("LunarLander_v2_remote-test-dataset")
```


## Saving to dataset format
It is not the aim of Minari to insist that you use a certain buffer implementation. However, in order to maintain standardisation across the library, we have a standardised format, the `MinariDataset` class, for saving replay buffers to file. 

This converter will have tests to ensure formatting standards

## Checking available remote datasets

```python
import minari

minari.list_remote_datasets()
```

## Checking available local datasets
```python
import minari
minari.list_local_datasets()
```



___

_Minari is a shortening of Minarai, the Japanese word for "learning by observation"._
