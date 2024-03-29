# 2024-03-29 12:52:08

I am trying to modify this repo so it
1. runs
2. I can monitor it's thoughts on difficult questions

Right now it seems to eval while hiding and discarding the thoughts. This happens in the modelling_mistral


Inference usually goes like this:
- generate some chain of thought, with hidden thoughts and public thoughts
- at some point prompt an answer
