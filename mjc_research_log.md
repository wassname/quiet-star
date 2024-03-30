# 2024-03-29 12:52:08

I am trying to modify this repo so it
1. runs
2. I can monitor it's thoughts on difficult questions

Right now it seems to eval while hiding and discarding the thoughts. This happens in the modelling_mistral


Inference usually goes like this:
- generate some chain of thought, with hidden thoughts and public thoughts
- at some point prompt an answer


what is 
- original_mode
- comparison_mode
- 

# 2024-03-30 11:42:55

I got it working but:
- the thoughts are mostly just completions or alternate paths. there is not much "secret thinking" revealed. This was a possibility since the thoughts were trained to be usefull, not to look good to humans
- the 7b model is not that great anyway
- maybe times that thoughts contradict each other, the answer, or are incohrent. So just like all chain of thought, it's not even clear that it represents thought
