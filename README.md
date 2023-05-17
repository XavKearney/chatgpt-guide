# Prompt engineering for non-technical people
ChatGPT has taken the world by storm this year. People around the world are using it for all kinds of tasks. New use cases are being discovered every day. 

But the interface is just text. You prompt ChatGPT with a message, and it responds. The content of your prompt can have a huge impact on the quality of the response, and how well it achieves what you intended. 

GPT-4, the latest of the OpenAI models, is incredibly powerful. Responses feel human, and it's easy to talk to in normal conversational language. But this is a trap! Typical human conversation only scratches the surface of what this model can do. This guide outlines a few tips for writing prompts that get more out of the model.

## Technical limitations
There are some important technical limitations to keep in mind:

- **Input size**: GPT-4 accepts large messages, but there's a limit. As a rough guide, it can handle ~4000-6000 words, but it depends on the content.
- **Output size**: The length of the output it gives is also limited. There's a trade-off between input and output. The longer your input, the shorter the output can be. The total input+output must be less than ~4000-6000 words.
- **Memory**: GPT-4 has no memory outside of a conversation. The only context it has is what it's seen so far in the conversation. If the conversation goes on too long, it will exceed the input size and the model will start to 'forget' the first messages.
- **Training data**: The model has only been trained on internet content from pre-2021. It has no knowledge of recent events (but that doesn't mean you can't bring it up to speed).


## Use cases

Here are a few examples of potential use-cases that might provide some inspiration for how to get the most out of GPT-4 in your day-to-day:

- Summarisation: 
    - summarise the key points in this news article/scientific paper"
    - "take this meeting transcript and summarise the key decisions made as bullet points"
    - "pick out the top 3 themes people mention in this list of feedback"
- Editing/formatting
    - "reword this feedback so it sounds more encouraging"
    - "rewrite this technical document in plain English"
- Coaching
    - "I'm not enjoying my job, help me figure out how to get more energy"
    - "I've received some feedback from my manager, let's discuss how I can act upon it"
    - "help me debug this code, it's giving me this error"
- Collaborating
    - "let's brainstorm some ideas for new marketing campaigns"
    - "help me write my wedding speech, I need some ideas for themes"
    - "let's draft a project plan for an upcoming initiative at work"
- Recommending
    - "where should I go on holiday with 3 kids in May if I want some sun?"
    - "what are some good books to read on holiday if I enjoyed [book title]"

For any of these use cases, the prompt you use will make a big difference to the results you get.

*If you have suggestions for more use cases, let me know, or submit a PR.*

## Maximising prompt effectiveness

Here are some tactical tips to help you make the most out of your conversations.

### Include as much context as possible
GPT-4 has effectively memorised all of the information on the pre-2021 Internet but that doesn't mean it has the context it needs to solve your problem. Providing the model with more context helps it to focus in on the knowledge that's most important, enabling more specific answers. 

Instead of asking:

```
Where should I go on holiday this year?
```

Try asking:

```
I'm planning a trip for me and my girlfriend. We're both 28 years old and live in London, UK. We love hiking and trying new foods. Recently we've enjoyed trips to Mexico and Argentina. We want to go away some time next year between January and May, for around 2 weeks. Where should we go?
```

You can even be explicit that you're giving the model context. Sometimes this makes it faster to incorporate:
```
# Context
Travellers: Tom (28 years old) and Hannah (28 years old), partners living in London, UK
Interests: Hiking and food
Recent enjoyable trips: Mexico and Argentina
Ideal time period: January - May
Duration: 2 weeks

# Question
Where should these travellers go on holiday?
```

Taking this to the extreme and pushing the limits of the model's context window (~4000-6000 words) enables less obvious use cases too:

```
# Context
[Paste the raw transcript from a meeting recording here]

# Request
Summarise this meeting transcript into bullet point notes, separating key decisions made and any action items.
```

### Use delimiters for more complex requests
In the larger prompts above we use delimiters (like `# Context`) to help the model separate different information in the prompt. This often makes it easier to write the prompt, too, as you don't have to worry so much about weaving information in neatly. You can use any delimiters you like, but GPT-4 is particularly familiar with Markdown so `#` characters work well.

If you want to include quotes, raw text or code, it's often more effective to delimit these with Markdown quotes:
````
Here's some code I wrote:
```
[code here]
```
How could I improve it?
````

### Be specific about the role you want the model to play
The model has been trained on all forms of content: people teaching, people debating, people speculating, people complaining, people lying etc. And this content has been written by a wide range of people, from world experts to people who have no idea what they're talking about. If you ask GPT-4 a question, it will answer based on some mix of all of those different kinds of content.

Often you don't want the average response, you want the expert response. Perhaps you don't want the empathetic response, you want the cold hard truth. The model is inherently unpredictable, so to increase your chances of getting the kind of response you want, be specific:

```
You are a helpful travel planner, with particular expertise in Asian holidays.
[...]
```
```
You are a kind and empathetic life coach. 
[...]
```
```
You are a bot for summarising meeting transcripts.
```

Getting creative with different roles will open up new use cases. You can never 100% guarantee it will adopt the exact role that you want. Being more specific or using more constraints will help.

### Use constraints
As well as providing context, it's important to include constraints if you have a particular desired outcome in mind. 

You might want to specify a response length:

```
[meeting transcript notes]
Summarise this meeting transcript. Do not use more than 5 bullet points.
```

Or specify a particular tone:

```
Explain how English football differs from American football. Use a biased perspective that is favourable to English football. Do not include any positive statements about American football. 
```

Or specify who needs to be able to read the response:

```
Explain String theory in 100 words. Do not assume the reader has any physics expertise beyond high-school physics.
```

Or specify a particular output format:

```
Respond with something I can paste directly into Google Sheets.
```
```
Respond in JSON.
```
```
What's 12 x 12? Respond with just the answer. Do not include any working out.
```

### Give feedback and iterate
GPT-4 has an incredible ability to learn and adapt on the fly based on your feedback. If you don't get the response you're looking for first time, don't despair! Explain to it why the answer didn't suit your requirements and work with it to get where you want to go. 

You can think of this like generating more context for the model. Instead of giving it all of the context up front, as you have a conversation you are creating context that informs the next response. Sometimes it can be more effective to take this iterative approach than try and perfect your prompt ahead of time.

You can even ask GPT-4 to suggest how you might improve your prompt for next time.

### Work through step-by-step
One quick hack that can help get better (more accurate) answers is to ask the model to talk through it's thinking step-by-step. This reduces the chance that it makes a mistake as the final answer benefits from all of the context written before it.

```
How many calories does a human consume in their lifetime? Give your step-by-step working.
```

```
Create a 6 week training plan for me at the gym. I want to lose weight and build muscle, particularly in my core. Explain your thinking before giving the answer.
```

## Things to watch out for

The model architecture and its technical limitations result in some practical limitations that are important to watch out for:

- Generally GPT-4 will perform worse at numerical calculations. One way around this is to ask it to give you the calculation to run yourself. It's not a calculator.
- It will occasionally 'hallucinate' (i.e. make things up). Often what it makes up will sound incredibly plausible and believeable. This is most common when asking it to recall specific information (e.g. "Recommend me a scientific paper about X from 1994"). It should be less of an issue with constrained tasks ("Summarise this text").
- The model is inherently random, so you will never get the same response twice for anything but very constrained queries. This does mean sometimes you can benefit by simply trying again with a fresh conversation.
