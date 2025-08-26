# My rules for a saner LLM vibecoding experience

## Setup steps:

#### Note: substitute "cursor" in steps below with Windsurf/Claude/etc

1. clone this repo outside other repos: `git clone https://github.com/ryandagg/cursor-repo-rules.git`,
2. Symlink rules into local repo: `ln -s ./cursor-repo-rules/rules/* /path/to/consuming/repo/.cursor/rules`,
3. Install these local MCP servers into Cursor
   1. [Memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory)
   2. [Sequential Thinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking)
   3. [Documentation Context](https://github.com/upstash/context7)
4. Consider adding these to your user level ~/.gitignore for
   1. .cursor
   2. tasks-\*.md
5. Open your repo in Cursor
6. ask the agent: `Use the @000-initialization.mdc rule to initialize this project.`

## Usage:

From there you can use the task management system by asking cursor:

```
Please create tasks using the @020-tasks-management.mdc workflow for the following work item:
```

_Paste the description of the ticket content, make sure to use @ syntax to include any relevant files_

Then the agent will create tasks in ./tasks/task-1.md, which you can review for accuracy, and when you're ready to try it out just tell the agent:

`Proceed with implementing Task ID: 001`

And it should have all the context it needs to do the thing.

There's also a code reviewer rule you can include in a request to review a PR, if you have the Github MCP server configured you can just provide a link to the PR and it will look up the PR.

There's a retro rule you can use to refine your rules as the project changes over time.

## TODO:

- Create a user-friendly bash script to move new rule files to this repo locally and symlink them back into the consuming repo.
- find a better approach than manual symlink setup. Nested repos used to be tedious/confusing, but now? 
