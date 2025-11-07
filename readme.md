1.需要nodejs、claudecode、githubcopilot 

2.npm install -g copilot-api

3.终端输入copilot-api start
用给出的url进行github授权

4.编辑~/.claude/settings.json

{
  "env": {
    "ANTHROPIC_BASE_URL": "http://localhost:4141",
    "ANTHROPIC_AUTH_TOKEN": "ink",
    "ANTHROPIC_MODEL": "claude-sonnet-4-5-20250929",
    "ANTHROPIC_SMALL_FAST_MODEL": "claude-haiku-4-5",
    "DISABLE_NON_ESSENTIAL_MODEL_CALLS": "1",
    "CLAUDE_CODE_DISABLE_NONESSENTIAL_TRAFFIC": "1"
  },
  "hooks": {
    "PostToolUse": [
      {
        "matcher": "Edit|Write",
        "hooks": [
          {
            "type": "command",
            "command": "ruff check --fix $CLAUDE_FILE_PATHS && black $CLAUDE_FILE_PATHS"
          }
        ]
      }
    ]
  },
  "alwaysThinkingEnabled": false
}


5.在任何终端输入claude启动。
