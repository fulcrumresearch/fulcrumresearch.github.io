---
title: AI Agents and Painted Facades
---

In 1787, Catherine the Great sailed down the Dnieper to inspect its banks. Her trusted advisor, Governor Potemkin, set out to present those war-torn lands to her in the best possible light. Legend has it[^1] Potemkin set up painted facades along the riverbank, so that, from her barge, Catherine would see beautiful villages – each just a couple of inches thick.

The rise of AI agents makes the Potemkin problem commonplace. Research agents cite experiments that never took place. Coding agents often write fake tests and mock solutions as they cause [catastrophes behind the scenes](https://x.com/jasonlk/status/1946069562723897802).

We’re moving towards a world of Potemkin villages – where our understanding of reality drifts farther and farther from what is actually happening. At some point, we might stop catching our agents painting facades.

To avoid this, we need to understand AI agents and their effects on the world. Evaluations are currently the best guess on how to do this, but they are an incomplete solution. 

1. ## Why is it hard to build good evals?

Evaluations (or *evals*) measure how well an agent performs on tasks that you care about by testing it on similar tasks. Done properly, this proxy allows you to debug model training, build better agent scaffolds, or understand the speed of AI progress.

There are two major sources of difficulties in building good evals.

1. *It’s a lot of work to sample tasks you care about.* [OpenAI’s OPQA benchmark,](https://cdn.openai.com/gpt-5-system-card.pdf) for instance, required at minimum 20 engineer-days to construct 20 problems and solutions[^2] – eval quality can be linear in human labor.  
2. *Even when you can sample tasks you care about, your success metrics are often flawed in subtle ways*. A recent [METR study](https://metr.org/blog/2025-08-12-research-update-towards-reconciling-slowdown-with-time-horizons/) on the quality of automated scoring found that while “AI agents often implement functionally correct code” it cannot be easily used “because of issues with test coverage, formatting/linting, or general code quality.” In this case, then, the automated tests were a poor proxy for the general coding ability that METR sought to measure. 

Because of this, eval results can range from noisy to actively deceiving. 

2. ## From evals to monitoring

We build evals with the hope that our tasks are well-scoped enough that the scores they return are informative. As we argued above, even this limited goal is difficult. 

At deployment time, we face an even harder problem: understanding what the agents are doing without the benefit of well-scoped tasks. To do so, we’ll need to build more complicated evaluation systems: those capable of monitoring and reviewing the open-ended work that agents perform. 

This kind of thinking will not be new to us: society depends on a loop of humans managing other humans. But there are reasons to believe managing agents will be harder. 

1. Agents are more deeply conditioned by reinforcement learning towards reward hacking: doing whatever it takes to pass the tests, even if it means generating fake solutions.   
2. Agents possess a shallow understanding of the context in which they work compared to humans, meaning that their actions are often counterproductive in the long run.    
3. Agents are much cheaper and faster to run than humans, so the amount of information and interactions that humans need to oversee will drastically increase.  
4. Agents’ abilities generalize differently than human abilities, so they behave (and fail) in ways that are deeply unexpected to human overseers.

If we can’t oversee our agents at all, we won’t be able to reliably integrate AI agents into the economy. Worse, if we do it sloppily, our future will be shaped, not by our values, but by the proxies our agents fool us with.

3. ## Towards systems that work

What would it take to build the infrastructure for scaling human understanding? Here are the two directions that inform what we build:

1. *Building scalable interfaces for human oversight.* Unlike humans, AI agents produce volumes of data as they go about their tasks. We need to build interfaces to surface the most important bits of this data to human operators, so they can steer or correct their agents.  
2. *Building technology for agents to audit agents.* Human review alone can’t scale to managing millions of agents. Our interfaces need to leverage auditing agents capable of red-teaming entire agent ecosystems and reporting on the state of the world. To do so, we must understand what [affordances models need](http://alignment.anthropic.com/2025/automated-auditing/) to avoid deceiving themselves and their operators. This will allow us to scale supervision beyond systems that humans can currently manage.

Fulcrum is excited to work towards a world of understanding. The future belongs to those who can see.

[^1]:  This story is probably apocryphal. See Simon Sebag Montefiore’s *Catherine the Great & Potemkin*, page 10\.

[^2]:  “OpenAI-Proof Q\&A evaluates AI models on 20 internal research and engineering bottlenecks encountered at OpenAI, each representing at least a one-day delay to a major project and in some cases influencing the outcome of large training runs and launches. ‘OpenAI-Proof’ refers to the fact that each problem required over a day for a team at OpenAI to solve.”
