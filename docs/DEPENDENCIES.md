# PM Agent Dependencies

## Required Dependencies

### Pencil MCP (Required for Prototyping)

Pencil MCP is required for the prototype design functionality in `/pm:design`.

**Installation:**

1. Install Pencil MCP server:
```bash
# Follow Pencil MCP installation guide
# Typically involves npm install or manual setup
```

2. Configure Claude Code to use Pencil MCP:
```json
// In your Claude Code settings
{
  "mcpServers": {
    "pencil": {
      "command": "path-to-pencil-mcp",
      "args": []
    }
  }
}
```

**Verification:**
```
/pm:design should be able to create .pen files
```

## Optional Dependencies

### Git (Recommended)

Used for version control and committing documents.

**Installation:**
- macOS: `brew install git`
- Windows: Download from https://git-scm.com
- Linux: `sudo apt install git`

### Markdown Preview (Optional)

For viewing generated PRD documents.

**Recommended:**
- VS Code with Markdown Preview Enhanced extension
- Typora
- Any Markdown viewer

## Dependency Detection

PM Agent will check for dependencies when running `/pm:init`:

| Dependency | Required | Check |
|------------|----------|-------|
| Pencil MCP | Yes | MCP tool availability |
| Git | Recommended | `git --version` |

## Troubleshooting

### Pencil MCP Not Found

If `/pm:design` fails with MCP errors:
1. Verify Pencil MCP is installed
2. Check Claude Code MCP configuration
3. Restart Claude Code

### Git Not Available

If git commits fail:
1. Install git
2. Configure git user: `git config --global user.name "Your Name"`
3. Initialize repo: `git init`
