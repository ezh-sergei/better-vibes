# Better Vibes

Opinionated set of rules for agentic coding with Cursor. Adopted ideas / approaches from various blogs, forum posts, discord chats and iterated on / evolved them as I was using them over the last few months.

## Context

I developed a set of rules over the last 6 months as I've been building a mobile app backed by a python backend with heavy llm workflows. Apologies for any overly specific rules that reference either React Native Expo or Python in here. I can keep these updated periodically if this is of interest to folks.

## Setup

You can use this set of rules for both a brand new project and an existing project.

- [ ] Clone/Fork/Copy the rules.
- [ ] Ask Cursor to clean the `code-*` rules of anything that doesn't match your project's needs.
- [ ] Copy or create the required folders if you'd like to start fresh. (`/docs/*`)
- [ ] Existing Project: Ask Cursor to `initialize your memory bank`. Depending on the size of your project, this might take many chats as the agent works through all of your code and all of your documentation that you have in the repo. Keep going until you feel the memory bank is well hydrated.
- [ ] Write your first spec notes and enjoy the Better Vibes.

## Workflow

### Write Spec Notes
  - I generally start with a couple of notes on what I want to do in a bullet point list in a Markdown file in `docs/prds/feature-name.md`.
  - Use PRD best practices to explain what you want. The better the quality of these notes, the better the output of the spec during plan mode.
  - Most of this happens over Superwhisper as that's generally faster than typing.
### Plan Mode
  - Initiate an agent in planning mode to do all the research about what I want to do: read code, libraries, read online resources and docs, ask me questions.
  - Slowly articulate and iterate towards a PRD that I think is a good level of depth for an agent to go execute on.
  - Once you're happy with the Spec part, ask the agent to convert your Notes using the PRD rules into a proper PRD and add a sequential implementation plan.
  - Ask the agent put all the details from research / context into the implementation notes section to hydrate it. The PRD template already contains all of these sections.
  - Iterate on the implementation plan itself - All the models are notoriously bad at picking the right level of detail to articulate steps. Ask for phases and stages if needed.
### Implementation Mode
  - Once I have a PRD, I kick off a new agent in implementation mode. One phase at a time.
  - If there are multiple phases that can be parallelized, I split them up into several background agents and have them cook in parallel.
### Debug Mode
  - Once an agent has completed a phase, I switch the agent over into debug mode, and depending on the task, either debug together (frontend) or have the agent debug in a loop with tests.
  - I usually spend a couple of cycles switching between debug mode and implement mode. This is usually enough to get through most problems.

## Notes and Gotchas

- Agents generally respond to imperative voice much better than to Q&A, So instead of asking them what do they think, tell them how they should be thinking.
- Sometimes agents forget to read the memory bank at the start of a chat. Telling them to do so explicitly I find works pretty well.
- Sometimes the agent gets confused whether they're planning or implementing. In those situations, I just use the keywords and trigger words to clarify it. This is what the headers are for for each of the modes so that it's very clear to you which ruleset the agent is applying.
- Sometimes you have to remind the agent to not write any code but actually do root cause analysis in debug mode. GPT is better at debugging than Claude or Gemini 2.5.
- I tried hard to make GPT-5 follow the Persona guidelines, but I couldn't take the autism out of that model. Use Claude or Gemini if you want to enjoy some of the chats with the agent.
- If you're planning with GPT-5, you will need to explicitly ask for sequential steps and phases that make sense. GPT-5 is pretty bad at task planning out of the box.

## Models

I mostly use Opus 4.1 and/or GPT-5-high for planning and then GPT-5 for implementation. Sonnet 4 is also pretty good at implementation and works with this ruleset well - I sometimes switch to that if I want more entertaining responses. Gemini 2.5 Pro works sometimes but usually gets stuck on tool calls and is generally less reliable.

## Questions or Suggestions?

All suggestions or questions are welcome - feel free to open an issue.
