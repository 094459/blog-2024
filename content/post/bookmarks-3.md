---
title: 'What I have been reading this week (1st March)'
date: '2026-03-01'
tags : [ bookmarks  ]
canonicalUrl: ""
---

![Bookmark Banner](https://ricsuepublicresources.s3.eu-west-1.amazonaws.com/images/bookmark-banner.png)

# Currently reading ( 1st March)

These are the current online posts that I enjoyed reading and made me think.

## AI


- AWS responsible use of AI guide (pdf) - [link](https://d1.awsstatic.com/products/generative-ai/responsbile-ai/AWS-Responsible-Use-of-AI-Guide-Final.pdf)  *[best-practice]* - ( Added: 2026-03-01 15:16:45 )

- Agentic AI is an amplifier, for both good and bad organisational behaviours. This post looks at some of the things you might observe for those who have not yet got their house in order - [link](https://flowchainsensei.wordpress.com/2026/02/22/ai-wont-save-your-dysfunctional-organisation/)  *[opinion]* - ( Added: 2026-03-01 13:12:29 )

- A good post on how to setup observability for your agentic applications.  - [link](https://www.glukhov.org/observability/observability-for-llm-systems/)  *[opinion]* - ( Added: 2026-03-01 10:32:37 )

- A neat tool that will help you right size LLMs for a given hardware spec. It detects your hardware, scores each model across quality, speed, fit, and context dimensions, and tells you which ones will actually run well on your machine. - [link](https://github.com/AlexsJones/llmfit)  *[tool]* - ( Added: 2026-03-01 00:24:15 )

- Another open source tool that allows you to "compact" your context and in the process help you reduce the input/output tokens used. Supports lots of common frameworks (Strands, LangChain, etc) and model providers (Amazon Bedrock) - [link](https://github.com/chopratejas/headroom)  *[tool]* - ( Added: 2026-02-28 19:53:17 )

- Research paper that looks at how to measure the reliability of agents - it proposes 12 metrics across four dimensions: 1/Consistency (does it behave the same across multiple runs?) 2/Robustness (does it handle and recover from tool failures - API errors, timeout, throttled, etc.?) 3/ Predictability (does the AI's confidence of success match reality?)  and 4/ Safety (how often does it violate constraints, and how severe are the failures?) - [link](https://arxiv.org/pdf/2602.16666v1)  *[best-practice]* - ( Added: 2026-02-28 14:47:35 )

- A benchmark that measures how models answer “bullshit” questions. It’s measured whether they push back (good) or go full on sycophantic and do it anyway. Why is this important? In an agentic flow, you want to have some confidence that your models are going to act/behave the right way when told to do stupid things. - [link](https://github.com/petergpt/bullshit-benchmark)  *[code-repo]* - ( Added: 2026-02-27 09:19:24 )

- Why running the Context Development Lifecycle over time produces a compounding advantage your competitors can't copy. - [link](https://tessl.io/blog/the-context-flywheel-why-the-best-ai-coding-teams-will-win-on-context/)  *[opinion]* - ( Added: 2026-02-26 14:20:47 )

- YT Video from The Pragmatic Summit. This session (panel) was titles "Building world-class engineering teams in the age of AI" with Thomas Dohmke (cofounder & CEO, Entire, previously CEO at GitHub) and Rajeev Rajan (CTO, Atlassian).  - [link](https://www.youtube.com/watch?v=fYh1CWadxDM)  *[video]* - ( Added: 2026-02-25 16:14:54 )

- Whitepaper that helps you figure out how to think about organisational adoption of AI - [link](https://www.thoughtworks.com/en-gb/insights/whitepapers/how-to-scale-ai-successfully)  *[best-practice]* - ( Added: 2026-02-25 16:09:54 )

- Essential reading - a number of reports that help you navigate the agentic AI landscape through tools like the AI capabilities framework and various reports. - [link](https://dora.dev/ai/)  *[best-practice]* - ( Added: 2026-02-25 16:08:30 )

- A look at how the Agentic AI Foundation (AAIF) grew to 146 members (including 97 new Gold and Silver companies), launched MCP Apps as a landmark OpenAI-Anthropic collaboration, and established a full governance structure with a Governing Board, Technical Committee, and seven working groups. - [link](https://aaif.io/blog/aaifs-first-quarter-success-story-new-members-technical-wins-and-open-governance/)  *[opinion]* - ( Added: 2026-02-25 13:40:15 )

- Book on what AI Native Engineering is - being developed in the open - [link](https://github.com/alfonsograziano/ai-native-engineering/blob/main/learning-path.md)  *[opinion]* - ( Added: 2026-02-25 09:55:56 )

- Techniques that you can use to reduce hallucinations when working with LLMs - [link](https://dev.to/aws/stop-ai-agent-hallucinations-4-essential-techniques-2i94)  *[best-practice]* - ( Added: 2026-02-25 09:52:16 )


---


## AWS


- An ebook from AWS that helps you analyse which foundational model is the best fit for your use case - [link](https://pages.awscloud.com/rs/112-TZM-766/images/AWS_eBook_LLM_FINAL%20%281%29.pdf?version=1)  *[best-practice]* - ( Added: 2026-03-01 15:09:27 )

- If you are looking to migrate to the cloud, one of the first steps you will need to complete is setting up your landing zone. This is the AWS prescriptive guide on how to set this up. - [link](https://docs.aws.amazon.com/solutions/latest/landing-zone-accelerator-on-aws/architecture-overview.html)  *[best-practice]* - ( Added: 2026-02-27 15:18:31 )


---


## CODING


- If you need to do any sort of local dev or testing with email, this project makes that easier. Nice and simple to get started, with great features and a nice UI - [link](https://mailpit.axllent.org/docs/)  *[tool]* - ( Added: 2026-03-01 13:28:21 )

- Must read post on the impact of agentic AI on the software developers lifecycle (SDLC) - [link](https://boristane.com/blog/the-software-development-lifecycle-is-dead/)  *[opinion]* - ( Added: 2026-03-01 13:15:17 )

- One of the best posts u have read on how agentic AI might impact and change software development. - [link](https://www.heavybit.com/library/article/write-only-code)  *[opinion]* - ( Added: 2026-03-01 12:56:38 )

- Looks super interesting- using Claude hooks together with deterministic tools to provide a new kind of workflow. - [link](https://nick-tune.me/blog/2026-02-28-hook-driven-dev-workflows-with-claude-code/)  *[opinion]* - ( Added: 2026-03-01 10:26:06 )

- New tool that can be used to ‘desloppify’ your vibed code. Looks interesting- installs a tool and is then run via a prompt. - [link](https://github.com/peteromallet/desloppify)  *[tool]* - ( Added: 2026-03-01 10:22:31 )

- Verified Spec Driven Development unified software engineering methodology that fuses three proven paradigms into a single AI-orchestrated pipeline: - [link](https://gist.github.com/dollspace-gay/d8d3bc3ecf4188df049d7a4726bb2a00)  *[opinion]* - ( Added: 2026-03-01 00:18:15 )

- Anthropic Claude Code skills training course - [link](https://learn.deeplearning.ai/courses/agent-skills-with-anthropic/lesson/ldn5c3/introduction)  *[tutorial]* - ( Added: 2026-02-26 22:18:00 )

- AWS Hero Matt Lewis shares some code snippets used as part of his session at re:Invent to showcase some different approaches to code migration/transformation - [link](https://github.com/mlewis7127/code-modernisation-strands-agent)  *[code-repo]* - ( Added: 2026-02-26 11:00:09 )

- An interesting idea - create functions without code, but with prompts, tests, and validators. Crazy or the future? You decide - [link](https://blog.mikegchambers.com/posts/software-31-ai-functions/)  *[opinion]* - ( Added: 2026-02-25 16:30:07 )

- A YT Video featuring Laura Tacho (dgx.com) on how organisations are really using/adopting AI coding tools - [link](https://www.youtube.com/watch?v=LOHgRw43fFk&t=1s)  *[video]* - ( Added: 2026-02-25 11:18:01 )


---


## OSS


- For commercial open source projects, agentic AI is creating new risks that allow anyone to reproduce your stack (NextJS, etc). Is it time to rethink how you manage your test suite? More questions than answers. - [link](https://simonwillison.net/2026/Feb/25/closed-tests/)  *[opinion]* - ( Added: 2026-02-28 21:17:15 )

- In this study, LF Research has tackled this question through the analysis of results from a survey and quantitative model on contribution ROI. Findings show that organizations spend hundreds of thousands of dollars maintaining private forks or developing internal workarounds, while those who choose to contribute upstream experience faster responses to security issues, increased development speeds, and easier talent retention. Reported benefit-to-cost ratios from OSS contributions are 2-5x on average, and the model estimates that contributing organizations yield a 6x ROI from their investments. - [link](https://www.linuxfoundation.org/hubfs/Research%20Reports/2025%20Open%20Source%20ROI%20Survey%202.23.26.pdf)  *[report]* - ( Added: 2026-02-27 12:12:33 )

- Redmonk take on oss and AI slop - [link](https://redmonk.com/kholterhoff/2026/02/03/ai-slopageddon-and-the-oss-maintainers/)  *[opinion]* - ( Added: 2026-02-24 22:25:44 )

- Impact of vibe coding on open source projects. Some great data points and much food for thought. - [link](https://www.infoq.com/news/2026/02/ai-floods-close-projects/)  *[opinion]* - ( Added: 2026-02-24 21:50:01 )


---


## TECH


- A great post on why a lot of developer programs fail, with opinions on how to fix that. It’s a hard problem for sure. - [link](https://www.builtfor.dev/blog/devrel-growth-playbook)  *[opinion]* - ( Added: 2026-02-27 09:24:43 )

- A great talk on the five immutable patterns of system design: evolvability, encapsulation, coupling, understanding, and failure. Well worth a watch - delivered silky smooth by James Eastham - [link](https://www.youtube.com/watch?v=EDwtofkScdI)  *[best-practice]* - ( Added: 2026-02-26 16:57:50 )

- Microsoft's take on understanding and then building resilient systems - contains some good slides to help you understand how to communicate these to stakeholders - [link](https://www.youtube.com/watch?v=vgOzZBAfMpA)  *[video]* - ( Added: 2026-02-26 14:48:10 )

- If you want to dive deep into best practices around newsletters, then look no more - this post is an incredible resource and provides great best practices. - [link](https://www.cjchilvers.com/blog/35-lessons-from-35-years-of-newsletter-publishing/)  *[best-practice]* - ( Added: 2026-02-25 16:12:33 )

- A good tutorial on setting up a prod gitops environment - Kubernetes (Amazon EKS / Karpenter) with argoCD. - [link](https://medium.com/@yawgyamfiprempeh27/eks-karpenter-argocd-from-zero-to-production-gitops-with-25-cheaper-ci-cd-pipelines-heres-8bd81d4d657b)  *[tutorial]* - ( Added: 2026-02-25 09:47:13 )


---





*Generated on 2026-03-01 by Bookmark Manager | 24th Feb 26 to 1st Mar 26 | Total bookmarks: 35*

Follow me on [LinkedIn](https://www.linkedin.com/in/ricardosueiras/) or [GitHub](https://github.com/094459)
