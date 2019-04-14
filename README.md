# Tensorflow Chatbot
Tensorflow Chatbot Demo by @Sirajology on [Youtube](https://youtu.be/SJDEOWLHYVo)

Overview
============
- This is the full code for 'How to Make an Amazing Tensorflow Chatbot Easily' by @Sirajology on [Youtube](https://youtu.be/SJDEOWLHYVo). 
- In this demo code, we implement Tensorflows [Sequence to Sequence](https://www.tensorflow.org/versions/r0.12/tutorials/seq2seq/index.html) model to train a chatbot on the [Cornell Movie Dialogue dataset](https://www.cs.cornell.edu/~cristian/Cornell_Movie-Dialogs_Corpus.html). 
- After training for a few hours, the bot is able to hold a fun conversation.


Dependencies
============
* numpy
* scipy 
* six
* tensorflow (https://www.tensorflow.org/versions/r0.12/get_started/os_setup.html)

Use [pip](https://pypi.python.org/pypi/pip) to install any missing dependencies

```
pip install numpy
pip install scipy
pip install six
pip install tensorflow==0.12.1

pip install -r ui/requirements.txt

# https://www.cs.cornell.edu/~cristian/Cornell_Movie-Dialogs_Corpus.html
mkdir data
cd data
wget http://www.cs.cornell.edu/~cristian/data/cornell_movie_dialogs_corpus.zip
unzip cornell_movie_dialogs_corpus.zip
mv "cornell movie-dialogs corpus"/* .

#https://github.com/llSourcell/tensorflow_chatbot/issues/55
python prepare_data.py

# outputs
λ ll data/*.enc
8630599174 -rw-r--r--  1 a1353612  184630988   1.6M Apr 13 16:25 data/test.enc
8630599172 -rw-r--r--  1 a1353612  184630988   5.9M Apr 13 16:25 data/train.enc

λ tail -f data/*.enc

==> data/test.enc <==
Ready for Fuchsmachen???
Three minutes to go!
Will you hear "Last Post", Sir?
You afeared of the Zulus then, Quartermaster?
Why don 't the Zulus attack?
Oh... indeed. Crealock, we should see that Colonel Dumford has an Officer for his hard riders. Perhaps a subaltern from the Twenty Fourth.
You intended to bring your reserves across the river?
Colonel Durnford... William Vereker. I hear you 've been seeking Officers?
Your orders, Mr Vereker?
Well I assure you, Sir, I have no desire to create difficulties. 45

==> data/train.enc <==
Yes?
Splendid site, Crealock, splendil I want to establish Camp here immediately.
Stuart?
How quickly can you move your artillery forward?
Well, fed or hungry, Pulleine wants them in position immediately. .
Lighting COGHILL' 5 cigar: Our good Colonel Dumford scored quite a coup with the Sikali Horse.
Do you think she might be interested in  someone?
Well that one. The one who keeps looking at me.
Choose your targets men. That's right Watch those markers. 55
Lord Chelmsford seems to want me to stay back with my Basutos.

```

Usage
===========

To train the bot, edit the `seq2seq.ini` file so that mode is set to train like so

`mode = train`

then run the code like so

```
python execute.py

```

To test the bot during or after training, edit the `seq2seq.ini` file so that mode is set to test like so

`mode = test`

then run the code like so

``python execute.py``


Challenge
===========

The challenge for this video is write an entirely different script using [TF Learn](http://tflearn.org/) to generate Lord of the Ring style sentences. Check out this very similar [example](https://github.com/tflearn/tflearn/blob/master/examples/nlp/lstm_generator_shakespeare.py), it uses TF Learn to generate Shakespeare-style sentences. Train your model on Lord of the rings text to do something similar! And play around with the hyperparameters to get a more accurate result. Post your GitHub link in the video comments and I'll judge it! 

### Due date: December 8th

Also see this issue, some people have found this discussion helpful
https://github.com/llSourcell/tensorflow_chatbot/issues/3

Credits
===========
Credit for the vast majority of code here goes to [suriyadeepan](https://github.com/suriyadeepan). I've merely created a wrapper to get people started. 
