---
title: Introducing Quibbler and Orchestra

---

Today, we’re excited to announce that we’re open-sourcing two tools:

1. [Quibbler](https://github.com/fulcrumresearch/quibbler) is a critic for your coding agent.

2. [Orchestra](https://github.com/fulcrumresearch/orchestra) is a multi-agent coding system: it uses a designer agent that spawns and coordinates your parallel coding agents. 


### Motivation

Human attention is a scarce resource. 

In the best case, coding with agents allows that attention to be spent on the “right” parts of your code: its functionality, architecture, and its failure-modes. In the worst case, your attention is spent on the behavior of your agents: preventing them from taking unsafe actions, asking them not to reward hack, and understanding if their outputs are trustworthy. 

Can we use agents to help us out?

### Quibbler 

Quibbler is a background agent that monitors and critiques your coding agent’s actions using hooks. Unlike most critics and guardrails, Quibbler is an agent: it can read and understand the context of an agent’s action to see if it made a mistake. 

We’ve found Quibbler useful in preventing agents from

1. fabricating results without running commands  
2. not running tests,   
3. not following your coding style

In longer running tasks, we found Quibbler useful in enforcing intent, allowing us to check in on our agent less. You can configure your guardrails, and Quibbler learns from your usage. Quibbler currently supports Claude Code: we are adding support for other agents soon\!

### Orchestra

Orchestra is a step towards true multi-agent coding: with parallel execution, active coordination, and full visibility of your coding agents. You plan with a designer agent, which spawns executors that work in isolated environments. When an executor needs help, it messages the designer agent (which gets your input if needed).

We’ve used Orchestra to: 

1. Iterate on the plan of a complex feature implementation and decompose it into bite sized subtasks  
2. Work on multiple independent features at the same time  
3. Implement features in a best-of-n style, where the designer merges the best result in after reviewing the code with you.   
4. Quickly review code with higher trust using our monitor

For both of these projects, we now have a 
To discuss with users and handle requests/

We also have an open [discord server](https://discord.gg/QmMybVuwWp) to engage with people using these new tools as we improve them.

## Looking Ahead

What are the properties of the interfaces that we will use to manage agents in real time? Here are some ideas:

1. Agentic validation: since human attention is the most expensive resource, we can spend agents compute liberally on falsifying or critiquing other agents’ results.     
2. Tree-like structure: users see high level context by default, but they should be able to “dig” into the work agents are doing in arbitrary depth. 

Real-time oversight of agent systems will be critical as agents scale beyond coding. At Fulcrum, we’re working on this problem. If you’re interested, we’d love to hear from you. We are hiring.
