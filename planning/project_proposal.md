# Project Proposal

Pod Members: **Add Pod Members Names**

## Problem Statement

Insert your groups problem statement and target audience.
# Project Proposal
Pod Members: **Jackie, Taliyah, Nathan**

## Problem Statement
Developers struggle to find open-source projects that align with their goals, tech stack, and learning interests. Even after identifying a potential repo, they often face barriers: understanding the codebase, evaluating whether it’s active or welcoming to contributors, and identifying where help is needed. The discovery process is fragmented and unintuitive.

## Description
Our tool aims to connect developers to open-source projects that match their preferences in topics, technologies, and contribution style. Using the GitHub API and Model Context Protocol (MCP), the platform will provide summarized, AI-enhanced insights into each project — such as tech stack, open issues, contribution guidelines, project health, and first-timer-friendly issues.

## Use Case Example
A user selects filters: JavaScript, frontend, climate change. The system returns 3 active open-source projects, each with a summary explaining their mission, active components, and how a newcomer can contribute today.

## Expected Features List
Key features:

Filter by programming language, tech stack, topics, and activity level.
MCP-powered project summarization (for example, “This project is focused on accessibility tools using React and Node.js, and needs help with frontend testing”).
Bookmark/save projects.
One-click views of good-first-issues or recent PRs needing review.

Stretch features:
Personalized recommendations based on prior contributions or stated goals.
Upon having an issue to target, the user will get suggested an area in the repository code to contribute into.

## Related Work
We were inspired by Hiring Cafe !
Similar apps and websites include: 
GitHub Explore
https://www.codetriage.com/?language=Erlang
https://libraries.io/ 

GitHub Explore and tools like Good First Issue, and CodeTriage offer curated lists of OSS projects. However, they lack contextual project summaries, they don't explain why a project might align with a developer’s goals, and there's no AI-powered insights into architecture or contribution needs.

## Open Questions
How might we implement MCP/AI functionality into the algorithm to search for open source projects?
How can we create a UI that reflects both intuitiveness and personality?
What is the most effective way to detail the functionality of a tool to an agent in an MCP user?
What are the limitations of our scope and how can we bear that in mind for the planning?

