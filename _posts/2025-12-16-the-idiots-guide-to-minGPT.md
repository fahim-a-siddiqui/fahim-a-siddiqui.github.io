---
layout: post
title: the idiot's guide to minGPT
date: 2025-12-16 0:00:00 +0600
tags:
  - ai
  - machine-learning
  - chargpt
---

It's kinda funny writing this as of the moment. I'm not much of a coder, but I really do like playing with ai models. I've wanted a simple model to play with. I first choose char-rnn but that shit is way too old to run on my laptop and has too many packages to be dependent on. Like, I'd never even heard of Lua before. That was why I opted for minGPT: simple, runs on Python, and looks modern without trying to look *modern*. 

I first had to download WSL on my crappy laptop that can't even hold an hour of charge. It took a few weeks to get used to it. Not because it was hard or something, but mainly because I'm just so easily distracted by other things. Like you know school and deciding what my creative passion should be (after much consideration, I opted for doodling).
 
Anyways, after getting used to WSL, I had to tour through github to find a nice looking character language model like char-rnn, which was created by Andrew Karpathy. Through some browsing, I found in his newer models something called minGPT. He also released nanoGPT but that seemed to be too advanced for my use. I just wanted to have fun with tiny neural networks. I didn't want to have something like caveman-ish ChatGPT running on my laptop yet.

So, with a lot of installation crap and a lot of hassle, I managed to get a workable form of minGPT on my laptop. I didn't understand a lot of the code in minGPT because it'd been a while since I first saw Python, so I had to enlist the help of ChatGPT and Visual Studio Code's AI Copilot to finish the job. Well, the job still isn't done, but you get what I mean.

I have all my code I talk about here on my GitHub profile. Just click on my profile and you'll see all the repos under my name. Also, you should note that the way my website renders code and how it doesn't highlight code in the webpage is done on intention. It's supposed to be like that, white text in IBM Mono in a black background while the rest of the article is in Verdana. 

Okay, I'm going to have to separate this article in headings for easer navigation. On second thought, maybe not. I'm not a very organized person. 

I run a Windows 11 on my computer, and originally installed WSL for char-rnn since the ancient packages it uses only runs on Unix operating systems like MacOS or Linux. WSL is like having a baby Linux on your Windows laptop. You get access to all the tools, packages, and even GUI apps which comes in real handy when you're trying to cd yourself through directories in the CLI. 

Before I used git to clone the minGPT repo in my WSL machine, I first created a virtual environment named 'ai-playground' (ChatGPT recommended me the name; don't judge me). A virtual environment, if you don't know, is like having a separate part of the house for a specific project. We create venvs (as they're shortened to) so we can have different versions of the same thing on our machine. Okay, let me give an example. 

Say, I want to test out a calculator app in my laptop that only runs on Python2 but I'm also testing out another project that is a tax-calculating app that only runs on Python1. And say, that my laptop already has Python3 installed beforehand. Instead of having three different versions of Python, I just have create a venv for the calculator app and another venv named something else for the tax-calculating app. Basically, venvs are there just to make everything tidy without having too many packages and different versions of the same thing. You get the idea? Well, let's move on. 

I activated my ai-playground venv by entering the following command in my linux kernel.

```
source ~/ai-playground/bin/activate
```

I then proceeded to git clone the minGPT and yada yada. I had to integrate VS Code with WSL before changing the code. By the time I'd paired VS Code with WSL, I was quite familiar with WSL and could navigate through the basics. I'm learning, though. 

I changed the code only for the chargpt project, because I wanted a character language model only; I wasn't interested in using the other features Karpathy had coded into the repo. I just wanted a simple tiny RNN (RNN: recurrent neural network), one that I could have fun with like predicating names, or you know ... stuff. Messing with AI models was the main reason I even started learning machine learning on my own. 

I still haven't uploaded my modified minGPT to GitHub, and I've still not fully customized it. I was thinking of adding a sample script so I could get samples when I'm not training the model, but I'm having difficulties with creating this sample script since I literally don't know Pytorch and am winging everything. I've also looked into another project called 'char-level rnn' on GitHub and am thinking of modifying it and using it. I've been liking minGPT, but it feels a bit too big for my usage. I want something more compact, and all I want is a simple character-level language model, okay? Nothing more, and the minGPT repo gives me much more. 

Anyways, I think it's time to show you the powers of minGPT and what it can do. To test out the minGPT/chargpt model, I first had to get a Hugging Face account and download a data set. The one I used was this: a [dataset of high-quality English sentences](https://huggingface.co/datasets/agentlans/high-quality-english-sentences). After renaming the file as 'input.txt', and putting it into the same directory as the chargpt.py file which, as I understood it, contained the major code for my character-level language model, I continued on. All I had to run this was enter the following command with the venv activated. 

```
(ai-playground) fahim717@FahimXPS:~/minGPT/projects/chargpt$ python chargpt.py
```

After running that crap, it'd give me the following prompt

```
Enter number for max_iters: 
```

Then I enter a number like, I don't know, 200 into the CLI. Note that I had to customize the trainer.py module in the main repo because the original chargpt apparently goes on forever. The original chargpt also doesn't save progress. I had to modify some files to do that, so that the tiny ai freakin remembers its training. 

Anyways, after that, the CLI gives me this: 

```
system:
    seed: 3407
    work_dir: ./out/chargpt
data:
    block_size: 128
model:
    model_type: gpt-mini
    n_layer: None
    n_head: None
    n_embd: None
    vocab_size: None
    block_size: None
    embd_pdrop: 0.1
    resid_pdrop: 0.1
    attn_pdrop: 0.1
trainer:
    device: auto
    num_workers: 4
    max_iters: 200
    batch_size: 64
    learning_rate: 0.0005
    betas: (0.9, 0.95)
    weight_decay: 0.1
    grad_norm_clip: 1.0

data has 22914134 characters, 583 unique.
number of parameters: 2.81M
Loading existing model weights...
running on device cpu
/home/fahim717/ai-playground/lib/python3.12/site-packages/torch/utils/data/dataloader.py:668: UserWarning: 'pin_memory' argument is set as true but no accelerator is found, then device pinned memory won't be used.
  warnings.warn(warn_msg)
```

I don't know what much of it means, but hey, I'm still learning, okay? So, this is what I get next.

```
iter_dt 0.00ms; iter 0: train loss 1.36114
Data: They had on it ways and become then, and smin predict world.
See have been positive to rapid the so some focused on the saunds.
It was considered in annurse tests should be considered up to have consumpted, they design to build such as the sending will be a served to take a fractory or compared by four spride to the damage.
The starting of the students of financial continues of the course of another task one of singers, it is a peakers.
This would at there.
Have a story to the product the fun an
saving model
```

I had modified the code of chargpt.py so it'd give me a sample every 100 iterations of training. Originally, the code would give you a sample every 500 iterations, but I wanted more samples. Note that I'd trained this model before. This is just further training. Since I asked for a maximum of 200 iterations of training, the code gave more stuff: 

```
iter_dt 1931.03ms; iter 10: train loss 1.34467
iter_dt 1917.43ms; iter 20: train loss 1.34919
iter_dt 4859.30ms; iter 30: train loss 1.27538
iter_dt 1901.91ms; iter 40: train loss 1.33289
iter_dt 1952.48ms; iter 50: train loss 1.30700
iter_dt 1940.13ms; iter 60: train loss 1.32701
iter_dt 1955.30ms; iter 70: train loss 1.34209
iter_dt 4629.48ms; iter 80: train loss 1.36487
iter_dt 1881.59ms; iter 90: train loss 1.40419
iter_dt 1922.78ms; iter 100: train loss 1.42617
Data: The contemporary trying in opening anniverse is created their crime infrastructure words.
Showing the for-different air is animal basis to see the extreme of the big paper spining is only a public for troop system and during the across the status intervention of properly strains that would be resulted that son't helps such as since that would do the resist.
So tie outer and the level in 1000 to have discovered a small thermall, the brainful and test determinate providers to the dreeing problem o
saving model
iter_dt 1905.38ms; iter 110: train loss 1.43142
iter_dt 1926.24ms; iter 120: train loss 1.40831
iter_dt 1989.14ms; iter 130: train loss 1.39474
iter_dt 1959.16ms; iter 140: train loss 1.38416
iter_dt 1917.20ms; iter 150: train loss 1.42199
iter_dt 4835.81ms; iter 160: train loss 1.40712
iter_dt 2049.69ms; iter 170: train loss 1.39645
iter_dt 2208.81ms; iter 180: train loss 1.36150
iter_dt 1938.14ms; iter 190: train loss 1.41002
```

See what it did there? It didn't print anything after the 200 iterations, cause the code terminates after that. The iteration message occurs every ten iteration, and when it reached 200, everything stopped, so the code looks like it stopped at 190, but actually it did some more. 

Chargpt has really made some gibberish shit. Like what is a 'saund'? Judging from the sentence 'The contemporary trying in opening anniverse is created their crime infrastructure words.', it is clear that chargpt hasn't learnt grammar yet. Well, it's not connected to the internet, so yeah, that's fair. Its only context is a stupid text of random English sentences. 

It was really fun to do this. I hope to mess around chargpt some more. And since my winter vacation has just started, I literally can't wait. 

