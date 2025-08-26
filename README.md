# My rules for a saner LLM vibecoding experience
  
## Setup steps:
1. clone this repo outside of other repos: `git clone https://github.com/ryandagg/cursor-repo-rules.git`,
2. `cd` to the root of repo to use these rules
3. Symlink rules into local repo: `ln -s /path/to/this/repo/* ./.cursor/rules`,
4. Install these local MCP servers into Cursor/Claude Code/Windsurf/etc
    1. [Memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory)
    2. [Sequential Thinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking)
    3. [Documentation Context](https://github.com/upstash/context7)
5. Consider adding these to your user level ~/.gitignore for
    1. .cursor
    2. tasks-*.md
6. ask the agent: ```Use the @000-initialization.mdc rule to initialize this project".```

## Usage:
From there you can use the task management system by asking cursor:
```
Please create tasks using the @020-tasks-management.mdc workflow for the following work item:
```
*Paste the description of the ticket content, make sure to use @ syntax to include any relevant files*

Then the agent will create tasks in ./tasks/task-1.md, which you can review for accuracy, and when you're ready to try it out just tell the agent:

```Proceed with implementing Task ID: 001```

And it should have all the context it needs to do the thing.

There's also a code reviewer rule you can include in a request to review a PR, if you have the Github MCP server configured you can just provide a link to the PR and it will look up the PR.

There's a retro rule you can use to refine your rules as the project changes over time.
