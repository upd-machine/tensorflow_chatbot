
```
python3.7 execute.py
execute.py:50: DeprecationWarning: The SafeConfigParser class has been renamed to ConfigParser in Python 3.2. This alias will be removed in future versions. Use ConfigParser directly instead.
  parser = SafeConfigParser()

>> Mode : train

Preparing data in working_dir/
2019-04-13 16:37:03.894438: I tensorflow/core/platform/cpu_feature_guard.cc:141] Your CPU supports instructions that this TensorFlow binary was not compiled to use: AVX2 FMA
Creating 3 layers of 256 units.
WARNING:tensorflow:From /usr/local/lib/python3.7/site-packages/tensorflow/python/framework/op_def_library.py:263: colocate_with (from tensorflow.python.framework.ops) is deprecated and will be removed in a future version.
Instructions for updating:
Colocations handled automatically by placer.
WARNING:tensorflow:From /Users/a1353612/soundofmusic/compile1010/tensorflow_chatbot/seq2seq_model.py:106: GRUCell.__init__ (from tensorflow.python.ops.rnn_cell_impl) is deprecated and will be removed in a future version.
Instructions for updating:
This class is equivalent as tf.keras.layers.GRUCell, and will be replaced by that in Tensorflow 2.0.
WARNING:tensorflow:From /Users/a1353612/soundofmusic/compile1010/tensorflow_chatbot/seq2seq_model.py:111: MultiRNNCell.__init__ (from tensorflow.python.ops.rnn_cell_impl) is deprecated and will be removed in a future version.
Instructions for updating:
This class is equivalent as tf.keras.layers.StackedRNNCells, and will be replaced by that in Tensorflow 2.0.
WARNING:tensorflow:At least two cells provided to MultiRNNCell are the same object and will share weights.
Traceback (most recent call last):
  File "execute.py", line 319, in <module>
    train()
  File "execute.py", line 137, in train
    model = create_model(sess, False)
  File "execute.py", line 104, in create_model
    model = seq2seq_model.Seq2SeqModel( gConfig['enc_vocab_size'], gConfig['dec_vocab_size'], _buckets, gConfig['layer_size'], gConfig['num_layers'], gConfig['max_gradient_norm'], gConfig['batch_size'], gConfig['learning_rate'], gConfig['learning_rate_decay_factor'], forward_only=forward_only)
  File "/Users/a1353612/soundofmusic/compile1010/tensorflow_chatbot/seq2seq_model.py", line 154, in __init__
    self.outputs, self.losses = tf.nn.seq2seq.model_with_buckets(
AttributeError: module 'tensorflow._api.v1.nn' has no attribute 'seq2seq'
```

fix: install tensorflow 1.1.0 using pip/ not pip3

```
λ python execute.py 

>> Mode : train

Preparing data in working_dir/
2019-04-13 16:55:31.434330: W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE4.1 instructions, but these are available on your machine and could speed up CPU computations.
2019-04-13 16:55:31.434349: W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use SSE4.2 instructions, but these are available on your machine and could speed up CPU computations.
2019-04-13 16:55:31.434354: W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use AVX instructions, but these are available on your machine and could speed up CPU computations.
2019-04-13 16:55:31.434359: W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use AVX2 instructions, but these are available on your machine and could speed up CPU computations.
2019-04-13 16:55:31.434363: W tensorflow/core/platform/cpu_feature_guard.cc:45] The TensorFlow library wasn't compiled to use FMA instructions, but these are available on your machine and could speed up CPU computations.
Creating 3 layers of 256 units.
Traceback (most recent call last):
  File "execute.py", line 319, in <module>
    train()
  File "execute.py", line 137, in train
    model = create_model(sess, False)
  File "execute.py", line 104, in create_model
    model = seq2seq_model.Seq2SeqModel( gConfig['enc_vocab_size'], gConfig['dec_vocab_size'], _buckets, gConfig['layer_size'], gConfig['num_layers'], gConfig['max_gradient_norm'], gConfig['batch_size'], gConfig['learning_rate'], gConfig['learning_rate_decay_factor'], forward_only=forward_only)
  File "/Users/a1353612/soundofmusic/compile1010/tensorflow_chatbot/seq2seq_model.py", line 106, in __init__
    single_cell = tf.nn.rnn_cell.GRUCell(size)
AttributeError: 'module' object has no attribute 'rnn_cell'
```
