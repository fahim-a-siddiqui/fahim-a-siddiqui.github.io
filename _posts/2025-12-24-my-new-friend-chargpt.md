---
layout: post
title: my new friend, chargpt
date: 2025-11-24 0:00:00 +0600
tags:
  - ai
  - machine-learning
  - chargpt
---
I've gotten a bit used to being a machine learning hobbyist. I'm liking the moniker a bit, and I've also gotten a bit used to chargpt. It's a bit slow, but the code seems familiar, and the environment feels like an old friend by this point. 

I still haven't mastered the linux kernel (that's going to take some time), so I feel like I haven't mastered ubuntu yet. There's still much to learn, and that excites me very much! For chargpt, I've deleted all the unnecessary files in the repo. I deleted all the readmes, and that jpg of that skiing boat, and the other adder model which I really didn't need since I only wanted a character level language model. I didn't want to spend my time on some model that can predict n numbers or whatever. 

In my current chargpt repo, there's only the essential minGPT files, some files for some additional requirements for minGPT, the projects file where chargpt is stored, a gitignore file which I left intact and untouched, and a setup.py file which seemed important cause it contained something that looked like code. 

I'm still working on that sample.py file. It's so difficult! I don't know how to do it. I need another week or two to solve this problem. I'm just so new to Pytorch and torch in general. 

I'm finding out a way to store old models for future use. I'd first thought about creating many duplicates of chargpt, but then I realized I could just copy the /out directory and move it in some folder, then delete it. Then I could replace the input.txt with another different file with the same name, and the model would create another /out directory. If you're not aware, the /out directory is where the model's training data resides. Delete it, and the model restarts anew. It's a bit tedious, and I haven't accomplished much. Character level language models take a lot of time to train! Woah, that's a mouthful to way. I think I'm going to call them Char-level RNNs now. Much shorter. 

If you're lazy to check the code out, this is how my current minGPT repo looks like. 

```
minGPT
    > minGPT.egg-info
	    - PKG-INFO
	    - SOURCES.txt
	    - dependency_links.txt
	    - requres.txt
	    - top_level.txt
    > mingpt
        > __pycache__
	    - __init__.py
	    - bpe.py
	    - model.py
	    - trainer.py
	    - utils.py
    > projects
	    > chargpt
		    > __pycache__
		    > out
		    - chargpt.py
		    - input.txt
		    - sample.py
	    > old models 
	- setup.py
```

As you can see, it's a whole lot! I didn't bother including the files from the pycache directories because they're not important. I assume they're just files to help python run better so they aren't directly linked to the project itself. 

I wanted a smaller repo with less files for easier maintenance, but I've grown too used to chargpt. It's easy to use, but yeah, got a lotta files here and there. I'll see what I can do about that. I also didn't include the files of the /out directory or the old models directory cause why not? Also because I am lazy, and it wasn't so important to include *them*. 

I haven't used chargpt that much yet. I only really trained it on one dataset, specifically the high-quality English sentence one. I found a dataset of rap lyrics on Hugging Face, and can't wait to see the results. Oh, a rapping AI! How hilarious it must be. It'll have to relearn the English language as well. I currently have chargpt training on a dataset of fairy tales. I haven't trained it enough to get actual legible results; it's still very much in the early phase. 

Anyways, onto training: this is what chargpt freakin gave me. 

```
Data: RxRCECD'x(`9Y(RqLErM'44QLqbLYYLK'LDe&8q(hedrxCEWYG(DGDxq4"VQwiLY`YCL7YxKO'{b(9O2bCjq"[DEd`(4:Q(thisucen c(RYYj'(4(K(LLwLE


b8CDqY(42`e wed 5"}h6"2e bS'e tore. b(PxChe
qxe 4`qKqY'e
'8e Y8ure R(RDDE
CEe bos 4DSY(O''E
'D8KevenSRE'e t8Kx'(D'erKenitOe (O8'(we
YqKqYEe mx(hed thifecxCOe YY8(w(huese w(A(R8Lhe whun'(whenqYe 5KD'8R(DDDD8'"K(A[her8(pqY"Du:R'"[w'K8erer8LDe bqq(Oe (8e w(OWqqeyDDx'(EK'Derev'K'q"R(DD'EKev'E 4MR'8e th'8ith(wDD8ere R8[wq(h"KEu:[hug8'8qKey p(Dq8e thechey Y(wDEe w'(8e wxxKEK8qe (
```

Clearly, the ai has fallen in love with brackets. Were there even brackets in the dataset? I don't know. I'll have to check. However, I don't really know why there would even be brackets in a fairy tale. What do you even need brackets for (maybe for math, and for occasions for when the author's too tired to haul in a footnote)?

Anyways, I'm going to play with chargpt now. I'll let you know the updates in the next post, if ... I'm still alive. MUWHAHAHAHA! Road accidents are common in Dhaka, I think. 
