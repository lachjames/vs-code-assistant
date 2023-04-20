# vs-code-assistant
Adds GPT-4 assistance to VS Code, allowing a collaborative development workflow.

## Features

### Can propose edits for your files

https://user-images.githubusercontent.com/4878272/233291853-b379515a-181d-4b5b-9b16-4b4f7a70b8a5.mp4

### Can reference multiple open files
It intelligently chooses which files to use for context, so it has enough context to answer the question without going over the GPT-4 token limit. At least, it tries to do this intelligently... it's actually harder than it sounds.


### Other features
 - I used React (mainly with pure HTML/CSS and `antd`) to develop the interface, with a focus on a really clean and professional design that integrates well with VS Code. I didn't want something that looks like a messaging app - I wanted it to _look and feel like a tool_ (but not to _act_ like one... looking at you, Bing).
 - Works in Dev Containers - this is a niche one, but I use them all the time so I really needed this to work.
 - Works great with Copilot - it's not a replacement for Copilot, but rather augments it for more complex problems (and lets you iterate/ask questions/give instructions). I use them both together with great success (though GPT-4 is undoubtedly better for complex tasks).

## Usage
The app is extension is free, open source, and MIT licensed. However, you will need an OpenAI API key (which you can set in the extension settings in VS Code - if you're not sure how, I'll leave it to you to Google it for nostalgia purposes, since you won't be doing much Googling once you get the assistant working!)

The app works best with `gpt-4`, but it was designed so the core functionality (the chat interface) would work with `gpt-3.5-turbo` (i.e. ChatGPT). Some of the more complex tasks, such as generating edits and picking files, will probably be beyond the capabilities of ChatGPT, but the codebase doesn't (currentlY) distinguish between the two... good luck, little AI!

## FAQ
**This is just Copilot X but (better/worse/open source/OpenAI-dependent/...**

Yes, this was inspired by Copilot X, but only in the sense that I saw it and thought "hey, someone should actually make that", because clearly Microsoft is in no hurry to do so...

If you'll allow me to opine for a moment, when Copilot X was announced I was extremely excited, until I read the FAQ and saw

> When will GitHub Copilot X be available and how much does it cost?
>_GitHub Copilot X is currently a representation of GitHub’s vision for the future rather than an available product offering of GitHub Copilot..._

Ah, so it's a concept of what they _could_ do in the future. Not cool Microsoft - you know that kind of bait and switch can break hearts. But hey, if you want to sue me for stealing your entirely original idea that "_X_ + AI = $$$", feel free.

_This is a little tongue-in-cheek - I get that these products take time, and doubly so when you're a corporation who, you know, has the responsibility to ensure AI doesn't go haywire (again, looking at you, Bing). I'm just salty because Copilot X looked cool, but for now it just seems like a "placeholder" for marketing... I can't wait for them to prove me wrong._

**This slows down VS Code**
There's a couple of small bugs floating around that seem to cause the interface to slow down over time (especially when using Jupyter Notebooks). It's entirely possible this is nothing to do with my extension, and instead is related to my development setup (which is using Dev Containers), so that's one reason I'm keen to publish this and get eyes on it! Please submit an issue if you have problems, and especially if you encounter a bug! Speaking of which...

**There's bugs!**
I'm an AI researcher by trade. That means I spend my time writing code, running it once, and then never looking at or using it ever again. That's not conducive to great quality coding, and while I try to develop my skills (e.g. by working on projects like this), 

**I want to use this, but I don't want to pay for OpenAI API access**
Hopefully it won't be long until we get some models of similar quality to ChatGPT that can be run locally, but it will _hopefully_ be quite a while until we get some models equivalent to GPT-4 that can be run by anyone. A fine-tuned version of LLaMA might be a great back-end for this, but it would require a powerful GPU to run it. Honestly, it's probably easier and cheaper to just pay OpenAI...

**I want to use this, but I don't have GPT-4 access**
Unfortunately, (although I have no evidence for this) I suspect it might be a while until OpenAI open access to GPT-4 for everyone. You can still join the waitlist and try your luck, and use ChatGPT (`gpt-3.5-turbo`) in the meantime.

**I used this to write some code, and it killed a puppy!**
I take NO responsibility for anything done with this tool, nor anything that happens as a result of this tool's usage (directly or otherwise). I reserve all rights under the MIT license, and offer no guarantees, warranty, etc. You should assume that everything this tool outputs is malicious code written by an expert developer whose sole purpose is to introduce bugs into your code without you noticing. I'm not kidding - GPT-4 is _not smart_, it's a probabilistic model that tries to predict the most likely continuation of text. If it thinks that a bug is more likely than the correct code, then that's what it will output. But even this is too generous, as GPT-4 is not _thinking_ at all - it's just predicting tokens, one by one, and has no ability to self-correct or edit its history. How would your code look if you could only ever write it once, from top to bottom with no jumping around, and had no opportunity to edit it? Would it work? Mine sure wouldn't.
