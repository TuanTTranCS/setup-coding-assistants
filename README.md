# AI Coding Assistants Setup Instructions


## Instructions for Setting Up AI Coding Assistants for Beginners

This guide provides step-by-step instructions for setting up popular AI coding assistants like GitHub Copilot and Cursor on various operating systems (Windows, macOS, and Linux). The content is based on official documentation, community resources, and manual reviews of AI-generated content.

AI coding assistants can significantly enhance your productivity and creativity. This guide will help you configure GitHub Copilot and Cursor using their free tiers. By the end, you'll be equipped to use these tools effectively for personal projects, schoolwork, or hackathons.

***Bonus Resource***: Check out my AI 101 slides summarizing best practices for AI Coding Agents and prompt engineering, originally presented at a local high school hackathon: [View Slides](https://tinyurl.com/tuan-t-ai-code-demo).

*Bonus*: I made a slide about AI 101 and summarize on Prompting Guides Coding Agent best practices for a recent workshop at a scraptyard hackathon for local highschool students. Can have a look [here](https://tinyurl.com/tuan-t-ai-code-demo)

> ***Note:** This guide was last updated on March 14, 2025. Due to the rapid evolution of AI tools, some details may become outdated. Always refer to the official documentation for the latest updates and features. Additionally, consider exploring emerging AI tools as the landscape continues to evolve.*

## Table of Contents
- [GitHub Copilot on VS Code (Free Tier)](#github-copilot-on-vs-code-free-tier)
  - [Setup Visual Studio Code](#setup-visual-studio-code-vs-code)
  - [Enable Copilot Free in VS Code](#enable-copilot-free-in-vs-code)
  - [Configuring System Prompts](#configuring-system-prompts)
- [Setting Up Cursor (Free Account)](#setting-up-cursor-free-account)
  - [Installation on Windows](#installation-on-windows)
  - [Installation on macOS](#installation-on-macos)
  - [Installation on Linux (Ubuntu)](#installation-on-linux-ubuntu)
  - [Setting Up Instructions (Rules) for Cursor](#setting-up-instructions-rules-for-cursor)
- [Copilot vs Cursor - A comparison](#copilot-vs-cursor---a-comparison)
- [Potential Conflicts between GitHub Copilot and Cursor](#potential-conflicts-between-github-copilot-and-cursor)
- [Conclusion](#conclusion)
- [Appendix: Alternative AI Coding Assistants](#appendix-alternative-ai-coding-assistants)
  - [Official Products](#official-products)
  - [Alternative Options for Self-Hosted AI Coding Assistants](#alternative-options-for-self-hosted-ai-coding-assistants)
  - [Low-Code and No-Code AI Options](#low-code-and-no-code-ai-options)

## GitHub Copilot on VS Code (Free Tier)

### Setup Visual Studio Code (VS Code)

Follow this guide from Microsoft to set up VS Code for your platform: [Click Here](https://code.visualstudio.com/docs/setup/setup-overview).


### Enable Copilot Free in VS Code

Follow this guide from Microsoft to set up GitHub Copilot on VS Code: [Click Here](https://code.visualstudio.com/docs/copilot/setup-simplified).

For someone preferring a video tutorial, here's a YouTube video: [![Video Tutorial](https://img.youtube.com/vi/thUxtOe0SQM/0.jpg)](https://youtu.be/thUxtOe0SQM?si=kdgY0Xn4RRzgKcaJ).

### Configuring System Prompts

System prompts help guide AI coding assistants to better understand your preferences and project requirements. Setting up effective system prompts can significantly improve the quality of AI-generated code.

#### Setting Up System Prompts in GitHub Copilot
Source: [GitHub Copilot Documentation](https://code.visualstudio.com/docs/copilot/copilot-customization)
GitHub Copilot allows you to configure custom instructions that influence how it generates code, test, code review and commit messages:

1. **Using Custom Instructions File**:
- Create a file named `.github/copilot-instructions.md` in your project root.
- Write clear instructions in markdown format about your coding preferences, style guidelines, and project-specific requirements.
- Copilot will incorporate these instructions when generating code suggestions.

Example of a `.github/copilot-instructions.md` file:

```markdown
# Project Coding Guidelines

## General Guidelines
- Use Python 3.9+ features and syntax
- Follow PEP 8 style guidelines
- Use type hints for all function parameters and return values
- Keep functions focused and small (max 20 lines)
- Include docstrings for all public functions and classes

## FastAPI Specific
- Use Pydantic models for request/response schemas
- Implement proper error handling with HTTP status codes
- Group related endpoints under router objects
- Use dependency injection for shared resources
- Include OpenAPI documentation for all endpoints

## Project Structure
- Place route handlers in `app/routers/`
- Store database models in `app/models/`
- Keep Pydantic schemas in `app/schemas/`
- Put business logic in `app/services/`
- Use `app/core/` for application configuration

## Testing
- Write pytest test cases for all endpoints
- Include both positive and negative test scenarios
- Mock external dependencies
- Test status codes and response structures
```

2. **Using VS Code Settings**:
- Open VS Code settings (Ctrl+, or Cmd+, on macOS).
- Search for "github.copilot.chat".
- Configure the following settings for different scenarios:
  - `github.copilot.chat.codeGeneration.instructions` for code generation
  - `github.copilot.chat.testGeneration.instructions` for test generation
  - `github.copilot.chat.reviewSelection.instructions` for code review

Example of VS Code settings for GitHub Copilot:
```json
  "github.copilot.chat.codeGeneration.instructions": [
    {
      "text": "Always add a comment: 'Generated by Copilot'."
    },
    {
      "text": "In TypeScript always use underscore for private field names."
    },
    {
      "file": "code-style.md" // import instructions from file `code-style.md`
    }
  ],

```

3. **Using Prompt Files**:
- Configure the `chat.promptFiles` setting to `true`.
- Create `.prompt.md` files in the `.github/prompts` directory.
- Write instructions using markdown formatting.
- Reference additional workspace files as needed.
- Attach these prompt files to chat requests using the "Attach Context" icon or Ctrl+/ (Cmd+/ on macOS).

Read more in the [Adding repository custom instructions for GitHub Copilot](https://docs.github.com/en/copilot/customizing-copilot/adding-repository-custom-instructions-for-github-copilot?tool=vscode#about-repository-custom-instructions-for-github-copilot-chat) and [GitHub Copilot Customization](https://code.visualstudio.com/docs/copilot/copilot-customization). 

## Setting Up Cursor (Free Account)

Cursor is an AI-enhanced code editor built on VS Code that offers powerful AI assistance. It provides a free tier with essential features that can be valuable during a hackathon.

### Installation on Windows

To install Cursor on Windows:

1. Visit the official Cursor website at [cursor.com](https://www.cursor.com/).

2. Click on "Download for Windows" to download the installer.

![Cursor download for Windows](/images/cursor-download-windows.png)

3. Once downloaded, locate the installer in your Downloads folder.

4. Double-click on the installer to begin the installation process.

5. Follow the on-screen instructions to complete the installation.

6. Launch Cursor after installation completes.

7. The application will prompt you to create an account or sign in. You can use the free tier without requiring payment information.

8. After signing in, you can start using Cursor's basic AI features immediately.

### Installation on macOS

For macOS users:

1. Go to cursor.com and click on "Download for Mac".

2. The cursor installer will be downloaded to your Downloads folder.

3. Double-click on the downloaded file to extract the installer. You may need to right-click and select "Open" if you receive a warning about an app downloaded from the internet.

4. Drag the Cursor app to your Applications folder.

5. Launch Cursor from your Applications folder.

6. Create an account or sign in when prompted. The free tier is available without payment information.

7. Once signed in, you can begin using Cursor's AI coding features.

### Installation on Linux (Ubuntu)

For Linux users, particularly Ubuntu:

1. Visit cursor.com and download the Linux installer (typically an AppImage file).

2. Open your terminal and navigate to your Downloads folder.

3. Make the AppImage file executable with the command:

```bash
chmod +x cursor-[version]-[build]-x86_64.AppImage
```
Example:
![Cursor chmod](/images/cursor-linux-chmod.png)

4. If you encounter an error about libfuse.so.2, install FUSE by running:
```bash
sudo apt-get install libfuse2
```

5. Run the AppImage file:
```bash
./cursor-[version]-[build]-x86_64.AppImage
```
Example:
![Cursor exec](/images/cursor-linux-exec.png)

6. For easier access, move the AppImage to the /opt folder:
```bash
sudo mv cursor-[version]-[build]-x86_64.AppImage /opt/cursor.appimage
```
From now you can open the app by running:
```bash
/opt/cursor.appimage
```
Source: [dev.to](https://dev.to/mesonu/how-to-install-cursor-ai-editor-on-linux-ubuntu-2025-update-3kji)

### Setting Up Instructions (Rules) for Cursor

Read from the source: [Cursor Rules](https://docs.cursor.com/context/rules-for-ai)

#### Cursor AI Rules Summary

*   **Purpose:** Control AI behavior with instructions or system prompts.
*   **Types:** Project Rules and Global Rules.

##### Key Points

*   **Project Rules:**
    *   Stored in `.cursor/rules`.
    *   Apply to specific parts of a project.
    *   Use semantic descriptions and file pattern matching.
*   **Global Rules:**
    *   Set in `Cursor Settings`.
    *   Apply to all projects (e.g., output language).
*   **Deprecated:** `.cursorrules` files are for backward compatibility and will be removed.


Setting up Rules for Cursor can be done both globally and on a project-specific basis:

#### Global Rules

1. Open Cursor Settings
2. Navigate to General > Rules for AI
3. Enter custom instructions in the provided text area
4. Click "Save" to apply the global rules

These global rules will apply to all projects you work on in Cursor.

#### Project-Specific Rules

1. Create a `.cursorrules` file in the root directory of your project
2. Open the file in a text editor
3. Add custom instructions for the specific project

Alternatively, Cursor is moving towards a new Project Rules system:

1. Create a `.cursor.json` or `.cursor-settings.yaml` file in the project directory
2. Define project-specific settings in this file, which can include AI preferences, development environment settings, and more

It's worth noting that the `.cursorrules` file method is being phased out, so it's recommended to transition to the new Project Rules system for better flexibility and control.

Both global and project-specific rules allow you to customize Cursor AI's behavior, including coding style preferences, best practices, and project-specific requirements. This customization helps ensure more accurate and consistent code generation tailored to your needs.
- Read more from Cursor101: [Click here](https://cursor101.com/article/cursor-rules-customizing-ai-behavior)
- And more awsome currsorrules across platforms, projects and languages: [Click here](https://github.com/PatrickJS/awesome-cursorrules)
- Tips on development with Cursors (Helpful for Front-End & Fullstack): 
[![Tips Video](https://img.youtube.com/vi/uJimjSDio_Y/0.jpg)](https://youtu.be/uJimjSDio_Y?si=HNDydaG6Mk5OkDPW)

## Prompting Guide
Learning effective prompt engineering can significantly improve your interactions with AI coding assistants. Here are some essential resources to help you master prompting techniques:
- Read from the official GitHub Copilot documentation: [Click here](https://docs.github.com/en/copilot/using-github-copilot/copilot-chat/prompt-engineering-for-copilot-chat)
- Learn from Microsoft's training module: [Click here](https://learn.microsoft.com/en-us/training/modules/introduction-prompt-engineering-with-github-copilot/)

## Copilot vs Cursor - A Comparison
- Reference: [Copilot vs Cursor (Feb 2025)](https://cosminnovac.medium.com/cursor-ai-vs-github-copilot-which-one-wins-45ba5828741f)

## Potential Conflicts between GitHub Copilot and Cursor
While GitHub Copilot and Cursor are both powerful AI coding assistants, there might be potential conflicts between them. [Read more](https://www.perplexity.ai/search/some-potential-conflicts-when-ssryqVDgRuSTIqwEz2VhJA).

## Conclusion

Setting up GitHub Copilot and Cursor with their free tiers provides powerful AI coding tools to enhance your development workflow. By configuring effective system prompts, you can further improve the quality and relevance of AI-generated code. Remember that these tools are meant to augment your abilities, not replace your critical thinking and problem-solving skills. Use them as collaborative partners in your coding journey, and they'll help you write better code more efficiently while learning from their suggestions.

## Appendix: Alternative AI Coding Assistants
If you're interested in exploring more AI coding tools beyond GitHub Copilot and Cursor, here are some alternatives worth considering (some of them have free tiers):

### Official Products

1. **Cody from SourceGraph**  
   - **Description**: Cody is an AI coding assistant integrated with SourceGraph, offering features like chat-based code generation and extensive context awareness. It supports VS Code, JetBrains, and Visual Studio.  
   - **Free Tier**: Yes, with monthly limits.  
   - **Link**: [SourceGraph Cody Documentation](https://sourcegraph.com/docs/cody)

2. **Windsurf AI from Codeium**  
   - **Description**: Windsurf is a free AI-powered IDE that offers rapid autocomplete suggestions and in-editor AI chat. It emphasizes user control and data security.  
   - **Free Tier**: Yes, with some limitations.  
   - **Link**: [Windsurf AI](https://codeium.com/windsurf)

3. **Devin AI**  
   - **Description**: Devin AI is an autonomous coding assistant capable of generating and assisting with complex code. It combines advanced reasoning and planning capabilities.  
   - **Free Tier**: No.  
   - **Link**: [Devin AI](https://devin.ai/)

4. **Bolt AI**  
   - **Description**: Bolt AI is designed to make prototyping faster and easier. It supports AI code generation, manual editing, and deployment, with features like framework and package support.  
   - **Free Tier**: Yes, with usage limits.  
   - **Link**: [Bolt AI](https://bolt.new/)

5. **Claude Code**  
   - **Description**: Claude Code is an AI-powered coding tool developed by Anthropic. It operates directly in the terminal, assisting developers with tasks like refactoring, debugging, and documenting code.  
   - **Free Tier**: Available as a limited research preview.  
   - **Link**: [Claude Code](https://docs.anthropic.com/en/docs/agents-and-tools/claude-code/overview)

### Alternative Options for Self-Hosted AI Coding Assistants

If you're interested in exploring alternatives to GitHub Copilot and Cursor, here are some self-hosted AI coding assistant options:

1. **Continue with Ollama**  
   - **Description**: Continue is a VS Code extension that integrates with custom models or LLM provider tools, such as Ollama or LM Studio, allowing you to run AI models locally. It supports models like CodeQwen and CodeLlama for real-time code completion and chat-based debugging.  
   - **Links**:  
     - [Continue Documentation](https://www.continue.dev/)  
     - [Continue Overview](https://youtu.be/qXNecVIxRi0?si=7wRCI_aEQvIAe33q)  
     - [Ollama](https://ollama.com/)  
     - [Continue with Ollama](https://dev.to/manjushsh/configuring-ollama-and-continue-vs-code-extension-for-local-coding-assistant-48li)

2. **Continue with LM Studio**  
   - **Description**: LM Studio is a desktop application that enables running Large Language Models (LLMs) locally. It supports various models, including those optimized for coding tasks, and can be integrated with VS Code for AI assistance.  
   - **Links**:  
     - [LM Studio Overview](https://lmstudio.ai/)  
     - [Continue with LM Studio](https://chriskirby.net/run-a-free-ai-coding-assistant-locally-with-vs-code/)

3. **TabbyML**  
   - **Description**: Tabby is an open-source, self-hosted AI coding assistant that supports major open-source LLMs like StarCoder and CodeLlama. It offers retrieval-augmented code completion and integrates well with VS Code.  
   - **Link**: [TabbyML GitHub](https://github.com/TabbyML/tabby)

### Low-Code and No-Code AI Options

Low-code and no-code platforms are becoming increasingly popular for creating AI-powered applications with minimal or no coding expertise. Tools like **Flowise AI**, **Vertex AI Agent Builder**, and **Zapier AI Agents** allow users to build AI agents quickly using visual interfaces and pre-built components. These platforms are ideal for rapid prototyping and making AI development accessible to non-technical users.

* Sources:
  - [Flowise AI](https://flowiseai.com)  
  - [Vertex AI Agent Builder](https://cloud.google.com/products/agent-builder)  
  - [Zapier AI Agents](https://zapier.com/agents)
