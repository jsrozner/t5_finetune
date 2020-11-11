Configure data_dir to have
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


To run tensorboard, just pip install tensorboard and then
tensorboard --logdir=<your save dir>
