# Axy Catalog

Official catalog of skills and agents for [Axy Web](https://github.com/Axy-Project/axy-claude-cli-web).

## Structure

```
skills/
  catalog.json     # Core skills (code review, deploy, git, etc.)
  java.json        # Java-specific skills (JPA, Spring Boot, etc.)
agents/
  catalog.json     # Agent templates (reviewer, architect, debugger, etc.)
```

## Contributing

Want to add a skill or agent? Open a PR!

### Adding a Skill

Add an entry to `skills/catalog.json`:

```json
{
  "id": "my-skill",
  "name": "My Skill",
  "description": "What this skill does",
  "category": "code",
  "trigger": "/my-skill",
  "source": "community",
  "author": "your-github-username",
  "promptTemplate": "You are an expert at... $ARGUMENTS"
}
```

### Adding an Agent

Add an entry to `agents/catalog.json`:

```json
{
  "id": "my-agent",
  "name": "My Agent",
  "description": "What this agent does",
  "category": "Code Quality",
  "role": "coder",
  "icon": "MA",
  "color": "#7c3aed",
  "model": "claude-sonnet-4-6",
  "source": "community",
  "systemPrompt": "You are a specialized agent that..."
}
```

## How Axy Uses This

Axy fetches these catalogs on startup and caches them. The catalog is refreshed every hour. If GitHub is unreachable, the last cached version is used.

## License

MIT
