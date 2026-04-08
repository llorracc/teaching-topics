# Class 10 — Job market guest lecture and Matsya workshop

**Date:** April 7, 2026

**Recording:** Zoom cloud recording for **180.606 Topics — Part 2** (~1h 53m); link in the meeting-assets email from Zoom (Apr 7, 2026).

> **Note:** The following is the **Zoom AI meeting summary** as delivered by email, converted to Markdown only (headings and list markup). Zoom’s transcript spells the tool “Matzia”; the econ-ark package is **[Matsya](https://github.com/econ-ark/Matsya)**.

---

## Meeting summary

### Overview

This lecture introduced students to Matzia, a specialized AI tool developed by the EconArc team for economics research analysis, particularly for Bellman equation-based models. The session focused on practical setup and configuration, guiding students through obtaining API keys, installing necessary software components, and integrating the tool with their existing research projects. Matzia represents a significant advancement in computational economics, serving as a heterogeneous agent model equivalent to Dynare for representative agent models.

### Key Concepts or Theories:

- API Keys: Authentication tokens that enable programmatic access to AI services, allowing integration into custom code and workflows
- Matzia: A bespoke AI tool designed specifically for economics research, named after the Indian deity equivalent to Prometheus who brought knowledge to humanity
- Dolo Plus: An enhanced language syntax for describing heterogeneous agent models, extending the capabilities of the original Dolo framework
- Claude Code: A command-line interface for interacting with Claude AI that provides deeper integration capabilities than standard chat interfaces
- Windows Subsystem for Linux (WSL): A compatibility layer for running Linux environments directly on Windows

### Important Questions Raised:

- How do API keys differ from standard chat-based AI interactions, and what advantages do they provide for research workflows?
- What is the relationship between Matzia, Dolo Plus, and existing tools like Dynare in the computational economics ecosystem?
- How can AI tools like Matzia assist in understanding and formalizing complex mathematical models in economic research?
- What are the cost implications and billing structures for using API-based AI services?

### Key Takeaways and Summary of Learning Objectives

- Students learned to obtain and configure Claude API keys for programmatic AI access
- The class successfully installed and configured Matzia, a specialized economics research AI tool
- Students gained experience with command-line tools and environment configuration across different operating systems
- The session demonstrated workflows for integrating multiple AI tools (Cursor, Claude Code, Matzia) in research projects
- Students learned about Dolo Plus as an emerging language for describing heterogeneous agent economic models
- The importance of proper file organization and directory structure for GitHub repositories was reinforced
- Students practiced troubleshooting technical issues with AI tools and development environments

### Topic 1: API Key Setup and Configuration

The session began with students obtaining API keys from Anthropic's Claude platform, a crucial step for accessing AI services programmatically. Students navigated to console.anthropic.com or platform.claude.com/dashboard to create accounts and purchase $5 in API credits. The process involved email verification, account creation (recommended via email rather than Google integration for easier future management), and payment setup. API keys differ fundamentally from chat-based AI interactions by enabling integration into custom code and applications, representing a "power user" approach to AI utilization.

A critical aspect emphasized was the one-time visibility of API keys—once generated, they cannot be viewed again, necessitating immediate secure storage in password managers or similar tools. Students learned that API billing operates on a prepaid model where services stop when credits are exhausted, requiring manual top-ups. This prevents unexpected charges but requires monitoring usage.

The configuration process involved adding API keys to Unix login files (.bashrc and .zshrc) to make them persistently available across terminal sessions. Students used one-liner commands to export environment variables, learning the distinction between temporary session-based configuration and permanent system-wide setup.

#### Relevant Q&A

Josh: Is it set up to automatically reload, or do you have to reload it manually?

Chris-JHU: Yes, you have to reload it manually. It will tell you when you run out of money, and it won't work until you put some more money in.

### Topic 2: Software Installation and Environment Setup

Students installed multiple software components including Claude Code, Node.js, and Python 3.11, learning about dependencies and package management. The installation process varied by operating system, with Mac users utilizing Homebrew and Windows users working within Windows Subsystem for Linux (WSL). This highlighted the importance of understanding one's development environment and the differences between operating systems.

The pip install command was used to install Matzia from the GitHub repository, demonstrating how Python packages can be installed directly from version control systems. Students encountered and resolved various installation issues, including missing dependencies like Node.js, which Claude Code requires to function. The troubleshooting process taught valuable lessons about reading error messages and consulting AI assistants for solutions.

For Windows users, a particular challenge involved ensuring all operations occurred within WSL rather than the native Windows environment, as the tools were designed for Unix-like systems. This required careful attention to file system locations and understanding the separation between Windows and WSL file systems.

#### Relevant Q&A

Student: I cannot see the folders locally. Could it be because I am using WSL all the time?

Chris-JHU: Yes, actually. So you'll need to clone the thing inside the WSL file system.

### Topic 3: Cursor Integration and Claude Code Setup

Students installed the Claude Code extension within Cursor, their integrated development environment, creating a powerful workflow combining multiple AI tools. The process involved navigating to the extensions manager (puzzle piece icon), searching for Claude Code, and installing it from the trusted publisher. This integration allows Claude AI to be accessed directly from the command line while working on projects.

Configuration required setting up environment variables for both the Anthropic API key and the Matzia-specific token. Students learned to distinguish between different types of credentials and their purposes—the API key for general Claude access and the Matzia token for accessing the specialized economics tool. The export commands added to shell configuration files ensured these credentials were available in every terminal session.

The session demonstrated the concept of context management in AI interactions, explaining that Matzia operates as an external tool without persistent memory of previous interactions. Each query must include necessary context, unlike Cursor's Composer which maintains conversation history. This architectural distinction is crucial for effective use of the tool.

#### Relevant Q&A

Chris-JHU: You need to really bear in mind that Matzia is a completely external tool which does not have access to anything in the file system that you do not feed to it directly. The composer cursor remembers what you've done before, but every time you make a query to Matzia, you have to make sure that it has the context that it needs to answer your question.

### Topic 4: Matzia Introduction and Capabilities

Matzia represents a significant advancement in computational economics tools, designed specifically for analyzing and working with heterogeneous agent models. Named after the Indian deity equivalent to Prometheus, Matzia brings advanced AI capabilities to economics research, particularly for models involving Bellman equations. The tool can read, analyze, and provide detailed descriptions of mathematical models in economic papers.

The development of Dolo Plus, an enhanced language for describing heterogeneous agent models, addresses a gap in the field. While Dynare provides an intuitive syntax for representative agent models, no comparable tool existed for heterogeneous agent models until now. Dolo Plus extends the original Dolo framework with capabilities necessary for modern macroeconomic research, allowing researchers to describe complex models in a standardized, machine-readable format.

Students learned to use Matzia through Cursor's Composer interface, feeding it Jupyter notebooks and asking it to analyze the mathematical content. The tool can validate Bellman problems, check for completeness, and generate Dolo Plus model specifications. This capability promises to streamline the process of formalizing economic models and ensuring mathematical rigor.

#### Relevant Q&A

Chris-JHU: What we're developing here is the new version of something like Dynare, but for heterogeneous agent models. One language that started doing that was a thing called Dolo, and we have added on to Dolo some important capabilities that it was missing, and that's why we have Dolo Plus now.

### Topic 5: Practical Application and Workflow

The session concluded with students applying Matzia to their previously created ballpark projects, demonstrating the complete workflow from setup to analysis. Students navigated to their ballpark directories, opened them in Cursor, and added relevant files to the AI chat context. The process involved asking Matzia to read and describe papers, validate mathematical formulations, and generate Dolo Plus model specifications.

Students learned to formulate effective queries for Matzia, understanding the importance of providing complete context in each request. For example, when asking Matzia to create a Dolo Plus model, students needed to explicitly reference "the notebook" to ensure Matzia had access to the necessary information. This differs from conversational AI where context is maintained automatically.

The practical exercise revealed Matzia's deep understanding of economic mathematics and its ability to explain complex concepts. Students were encouraged to use Matzia to clarify any aspects of their papers they found difficult to understand, leveraging the tool's analytical capabilities to enhance their own comprehension and improve their ballpark descriptions.

#### Relevant Q&A

Chris-JHU: You will find that you can ask Matzia all sorts of questions, and it has a deep understanding of the math. So if there's anything about the paper when you read it that you had trouble understanding, ask Matzia to explain that concept or to help you understand what's going on.

### Actionable Next Steps / Assignments

- Use Matzia to analyze and improve your ballpark project from earlier in the semester
- Ask Matzia for advice on how to improve any incomplete or unclear mathematical descriptions in your ballpark
- Request Matzia to construct a Dolo Plus model specification of the Bellman problem in your chosen paper
- If your original ballpark paper was purely empirical with no Bellman equation, select a different ballpark project that includes dynamic optimization
- Use Matzia to explain any concepts from your paper that you found difficult to understand during your initial reading
- Submit an improved version of your ballpark that incorporates Matzia's feedback and includes a Dolo Plus model specification by next week's class
- Ensure your API credits are sufficient for the assignment work (the initial $5 should be adequate)

### Supplemental Resources

- Anthropic Claude API documentation at console.anthropic.com and platform.claude.com/dashboard
- Matzia repository on GitHub at github.com/econ-ark/Matzia with comprehensive README and usage instructions
- Cursor IDE with Claude Code extension for integrated AI-assisted development
- Windows Subsystem for Linux (WSL) documentation for Windows users requiring Unix-like environment
- Dolo and Dolo Plus documentation for understanding the model specification language syntax

[View in Zoom](https://zoom.us/launch/hub?type=summary&mid=u3UJE0M%2BQoK%2BXAYuKSp6kw%3D%3D&origin=https%3A%2F%2Fzoom.us%2Fuser%2Fmeeting%2Fsummary%3FmeetingId%3Du3UJE0M%252BQoK%252BXAYuKSp6kw%253D%253D)

*AI can make mistakes. Review for accuracy.*

---

## Assignments in play (from Class 9)

Due before this class or ongoing — see [Assignments for Class 10](https://github.com/llorracc/teaching-topics/blob/main/assignments/for-class-10.md) (REMARK compliance self-assessment; SSJ tutorial exploration).
