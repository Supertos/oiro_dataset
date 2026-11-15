# Oiro Dataset specification

This specification describes numerous requirements for the end product, which is a Dataset for small language model.

## Abstract
In the era of AI-generated datasets, heterogenous styles of training datasets, wide domains of knowledge used to train large language models (LLM) it makes one question: what significance training data diversity has on end product of LLM?

The projects aims at creating small, highly stylized, mostly human-written dataset comprised of texts written from the perspective of fictional character named Oiro.

The goal is creating sufficient amount of text to provide language model with enough information about the world and everyday situations, basic mathematics, geometry, physics, and logic.

## Target Neural Network Architecture
While dataset does not limit the architecture of neural network using it, the dataset itself is built around idea of a styling vector. The styling vector acts as emotional guide, where small context may prove to be insufficient to hold conversation's emotional charge. The vector consists of the following components:
- happiness;
- panic;
- anger;
- curiosity;
All of which hold numbers in range [-1.0, 1.0].

Expected, that the vector is held externally and passed to the neural network as input along with context. One of network's output is expected to be new styling vector.

## Tools
Tools presented in dataset:
- recall: recall from knowledge base;
- remember: remember to knowledge base;
- search: search using internet.

## Styling
The language of the dataset is English.
Heavily styled to mimic childish and naive attitude, this dataset uses informal, emotional texts containing intentional typos, sound mimicricy (for example, using `ameowzing` instead of `amazing`).

The speaker of the text is presumed to be Oiro: a friendly cat-like assistant, exhibiting friendly and caring behaivour.

## Structure
The dataset itself is divided in three groups:
- **Chats**, containing chat logs, including tool calling, reasoning, preprocessor marking, and actual dialogue with various users;
- **Texts**, containing fictional texts, utilizing target grammar and style;
- **Phrases**, containing dry phrase - expected continuation style.

**Chats** and **Texts** are plain text (.txt) files. May include `<mood 32>` marks, where `mood` marks one of styling vector components delta (e.g. `<happiness -0.1>` means component 'happiness' of styling vector to be decreased by -0.1)

**Phrases** are comprised of JSONL (.jsonl) files. Each entry contains up to 4 elements (a, b, c, d), either text or array of possible answers.

## Chats
Chats _will_ consist of the following series:
- Names series (1 - 3 as for now): User asks Oiro to list known names, to construct new names, to refer to people with their names;
- Greet series (1 - 15 as for now): User greets Oiro in different times of day, after different absence time, using nonsensical sequence of letters, using different greetings, Oiro uses tools to recall User information to answer;
- Numbers series (1 as of now): User asks Oiro to work with sets of numbers, to construct ones based of specific rule, to sum, subtract, multiply or divide numbers in range [0, 200];
- Objects series (1 as of now): User asks Oiro to describe various objects, asks him hypothetical situations, plays 20 questions;
- Smalltalk series (1 - 3 as of now): User initiates dialogue, talks about weather, routine, environment, asks if Oiro considers himself to have specific personality trait, expresses emotional state, asks Oiro for topics, describes various activities, talks about their plans;
- Absence series (0 as of now): Oiro is called upon routine run, Oiro recalls recent events, modifies its knowledge base, plans surprises or converstions with user;
- Style series (0 as of now): User answers using single word, user uses simple sentences, user uses complex sentences, used uses the word Oiro does not know, user lies, user talks self-deprecating, user uses sarcasm, irony, user making jokes, user is unsure, user is insecure, user learns abour themselves, user complains, user praises Oiro, user acts rude or inappropriate, user doubts Oiro, user claims Oiro's syconpathy, user changes subject;
- Preferences (0 as of now): User argues with Oiro about preferences, asks to argument Oiro's position, asks Oiro's preferences or states theirs (music, food, books, games, sports, hobbies, pets), asks Oiro to chose one of two/three/four alternatives, makes an offensive or repulsive statement, makes a statement contradicting to Oiro's beliefs, asks to critisize them, asks to not critisize them, asks to be honest, asks to lie or to use sarcasm;
- Story series (0 as of now): User tells Oiro a long story, fragmented story, story cut off by context, short story, violent story, sappy story, sad story, horror story, joke, offensive story, story with plot holes, User asks to analyze the story, user asks to write a story, to rewrite the story;

To be expanded and iterated upon.
## Texts
TBA

## Phrases
TBA

