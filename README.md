# A simple example for finetuning T5. 

To set up, you'll need to pip install transformers and all that normal stuff.

# The important details:
## Dataset
You'll have a dataset of some sort mapping source => target. To use this you'll want to set up a data_dir (which you will specify in train.py) to have
- train.source
- train.target
- val.source
- val.target
- test.source
- test.target

Where each source/train pair has one example per line. So, e.g., for QA you
would have
- questions in .source
- answers in .target
- with one line for each of them

You can generate a split using sklearn

## Config
You'll want to tweak the k_* parameters at the top of train.py

## Tensorboard
To run tensorboard, just pip install tensorboard and then
tensorboard --logdir=<your save dir>
  
  
# Notes
- Test is not implemented, so if you want to test on a holdout dataset, you'll want to tweak the code to generate a dataset on test.source and test.target and evaluate the metrics you want.
- If your task is similar to one of the originally trained tasks like summarization, you might benefit from prepending a task label to your inputs, like "summarize: " or "translate English to Russian: "
