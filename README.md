# GitHub Issue Labeling Assistant

This repository contains tools and guidelines for automatically analyzing and suggesting labels for GitHub issues using AI assistance. It helps maintainers efficiently categorize issues based on difficulty, kind, priority, and status using a standardized labeling system.

## Overview

The labeling assistant analyzes GitHub issues from repositories (specifically designed for ethersphere/* repositories) and provides recommendations for appropriate labels without automatically applying them. This allows maintainers to review suggestions before applying labels.

## Features

- **Automated Issue Analysis**: Fetches all open issues from specified GitHub repositories
- **Label Recommendations**: Suggests appropriate labels based on issue title, description, and conversation
- **Standardized Labeling System**: Uses a comprehensive set of predefined labels for consistency
- **Tabular Output**: Provides organized results in an easy-to-review table format
- **Multi-dimensional Classification**: Analyzes issues across multiple dimensions:
  - **Difficulty**: `dif:trivial`, `dif:easy`, `dif:medium`, `dif:hard`, `dif:expert`
  - **Kind**: `kind:bug`, `kind:enhancement`, `kind:question`, `kind:architecture`, etc.
  - **Priority**: `P0` (Critical) through `P4` (Very low priority)
  - **Status**: `status:ready`, `status:blocked`, `status:in-progress`, etc.
  - **Needs**: `need:analysis`, `need:author-input`, `need:community-input`, etc.

## Prerequisites

- GitHub Personal Access Token (PAT) with appropriate permissions
- GitHub MCP (Model Context Protocol) server access
- AI assistant with MCP capabilities (e.g., Claude with MCP integration)

## Installation

### 1. GitHub Personal Access Token Setup

1. **Generate a GitHub PAT**:
   - Go to [GitHub Settings > Personal Access Tokens > Tokens (classic)](https://github.com/settings/tokens)
   - Click "Generate new token (classic)"
   - Set an appropriate expiration date
   - Select the following scopes:
     - `repo` (Full control of private repositories)
     - `public_repo` (Access public repositories)
     - `read:org` (Read org and team membership)
     - `read:user` (Read user profile data)

2. **Save your token securely** - you'll need it for the MCP configuration

### 2. GitHub MCP Server Configuration

#### Option A: Using Other MCP-Compatible AI Assistants

If using other AI assistants that support MCP, refer to their specific documentation for GitHub MCP server integration. The general pattern involves:

1. Installing the GitHub MCP server
2. Configuring the server with your GitHub PAT
3. Adding the server to your AI assistant's MCP configuration

#### Option B: Using Claude Desktop with MCP
1. **Install the GitHub MCP Server**:
   ```bash
   npm install -g @modelcontextprotocol/server-github
   ```

2. **Configure Claude Desktop**:
   - Open Claude Desktop configuration file:
     - **macOS**: `~/Library/Application Support/Claude/claude_desktop_config.json`
     - **Windows**: `%APPDATA%/Claude/claude_desktop_config.json`
     - **Linux**: `~/.config/Claude/claude_desktop_config.json`

3. **Add GitHub MCP configuration**:
   ```json
   {
     "mcpServers": {
       "github": {
         "command": "npx",
         "args": [
           "@modelcontextprotocol/server-github"
         ],
         "env": {
           "GITHUB_PERSONAL_ACCESS_TOKEN": "your_github_pat_here"
         }
       }
     }
   }
   ```

4. **Restart Claude Desktop** to apply the configuration


### 3. Environment Setup

1. **Clone this repository**:
   ```bash
   git clone <repository-url>
   cd labeling
   ```

2. **Review the labeling rules**:
   - Check `rules.md` for the complete labeling system
   - Familiarize yourself with the label categories and their meanings

3. **Customize the prompt** (optional):
   - Edit `prompt.md` to modify the analysis instructions
   - Adjust repository targets or analysis criteria as needed

## Usage

### Basic Issue Analysis

1. **Start your AI assistant** with GitHub MCP configured
2. **Load the project context** by referencing the files in this repository
3. **Run the analysis** using the prompt from `prompt.md`:

   ```
    Get all the open issues from ethersphere/... github repo and one by one depending on the title and the conversation advise labels for each issue, use the labels definied in rules.md. don't add any label yet, just give me a table. Use the code to detemine the difficulty and try to estimate priority and have a guess for the kind label. Then print CLI commands to add the labels to the issues while keeping the current labels.
   ```

### Customizing for Different Repositories

To analyze issues from different repositories:

1. Replace `ethersphere/...` in the prompt with your target repository
2. Ensure your GitHub PAT has access to the target repository
3. Verify that the labeling system in `rules.md` is appropriate for your project

### Understanding the Output

The analysis will provide a table with columns typically including:
- **Issue Number/Title**: GitHub issue reference
- **Kind**: Type of issue (bug, enhancement, question, etc.)
- **Difficulty**: Complexity level for contributors
- **Priority**: Urgency/importance ranking
- **Additional Labels**: Status, needs, environment-specific labels
- **Reasoning**: Brief explanation for label suggestions

## Label Categories

### Difficulty Labels
- `dif:trivial` - Can be confidently tackled by newcomers
- `dif:easy` - Someone with a little familiarity can pick up
- `dif:medium` - Prior experience is likely helpful
- `dif:hard` - Having worked on the specific codebase is important
- `dif:expert` - Extensive knowledge (implications, ramifications) required

### Kind Labels
- `kind:bug` - A bug in existing code (including security flaws)
- `kind:enhancement` - A net-new feature or improvement
- `kind:question` - A question or request for support
- `kind:architecture` - Core architecture of project
- `kind:discussion` - Topical discussion; usually not changes to codebase
- `kind:maintenance` - Work required to avoid breaking changes
- `kind:refactor` - Refactoring issue
- `kind:test` - Testing work

### Priority Labels
- `P0` - Critical: Tackled by core team ASAP
- `P1` - High: Likely tackled by core team if no one steps up
- `P2` - Medium: Good to have, but can wait until someone steps up
- `P3` - Low: Not priority right now
- `P4` - Very low priority

See `rules.md` for the complete list of available labels.

## Best Practices

1. **Review Before Applying**: Always review AI suggestions before applying labels
2. **Consistent Application**: Use the standardized labeling system consistently across issues
3. **Regular Updates**: Periodically re-analyze issues as they evolve
4. **Community Input**: Consider community feedback when labeling controversial or complex issues
5. **Documentation**: Document any custom labeling decisions for future reference

## Troubleshooting

### Common Issues

1. **GitHub PAT Permission Errors**:
   - Verify your PAT has the correct scopes
   - Check that the token hasn't expired
   - Ensure you have access to the target repository

2. **MCP Connection Issues**:
   - Restart your AI assistant
   - Verify the MCP server configuration
   - Check that the GitHub MCP server is properly installed

3. **Label Suggestions Don't Match Repository**:
   - Review and update `rules.md` to match your repository's labeling system
   - Customize the analysis prompt for your specific needs

### Getting Help

- Check the GitHub MCP server documentation
- Review your AI assistant's MCP integration guide
- Verify GitHub API access and permissions

## Contributing

To improve this labeling system:

1. Update `rules.md` with new or modified label definitions
2. Enhance `prompt.md` with better analysis instructions
3. Add examples of well-labeled issues for reference
4. Submit pull requests with improvements
