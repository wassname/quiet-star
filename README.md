# Experiments with seeing the secret thoughts of LLM's


I had a play with Quiet-STaR

It has "private thoughts" that have never been tuned to human preferences. I was curious about it's private thought.

- occasionally there is a glimpse of duplicity
- mostly is garbled, or unrelated like regular CoT
- curious about a larger model

The thoughts share these properties with normal Chain Of Thought
- the conclusion is sometimes not faithfull to the reasoning
- it's sometimes garbled (normal for a small 7b parameter model)

I think all these differences could become more distince in a larger model. And it's fascinating to see thoughts that have been trained to be effective, not to please humans. However some of the thoughts contradict each other, so it would be even nicer if we could somehow make sure that they are used, but this is an open research question.

Links:
- Main notebook: https://github.com/wassname/quiet-star/blob/main/main2.ipynb
- Tweet thread: https://twitter.com/wassname/status/1774709219884949928/photo/1

![image](https://github.com/wassname/quiet-star/assets/1103714/bf4d66a3-979b-442b-a407-fc312d118800)

# Quiet-STaR

Code for [Quiet-STaR: Language Models Can Teach Themselves to Think Before Speaking](https://arxiv.org/abs/2403.09629).

This project is implemented by simply patching the base Mistral implementation in Huggingface `transformers` using a new `modeling_mistral.py` and a new `configuration_mistral.py` and otherwise applying standard `transformers` features (e.g. the default Trainer). Our patches were applied to Huggingface's `transformers` version `4.37.0.dev0` under `src/transformers/models/mistral/` -- we cannot guarantee that other changes to their implementation will not affect our implementation, so for reproducibility, we encourage using the same version.

One pitfall to be wary of: the model is not taught not to generate start and end thought tokens. Thus, when performing actual inference, it is necessary to mask these out.

We make an 8-thought-token ahead (including start and end tokens) model [available via Huggingface](https://huggingface.co/ezelikman/quietstar-8-ahead).
