# OpenClaw Skills Collection

A curated collection of skills for [OpenClaw](https://github.com/openclaw/openclaw) - a self-hosted AI gateway connecting messaging apps to AI agents.

## Skills

| Skill | Description | Install |
|-------|-------------|---------|
| [openclaw-whisperer](./openclaw-whisperer/) | Diagnostic, error-fixing, and skill recommendation tool for OpenClaw | `npx clawhub@latest install openclaw-whisperer` |
| [skill-hub](./skill-hub/) | Skill discovery, security vetting, and installation hub (3000+ curated skills) | `npx clawhub@latest install skill-hub` |
| [skill-vetting](./skill-vetting/) | Security and utility assessment for ClawHub skills before installation | `npx clawhub@latest install skill-vetting` |
| [openclaw-backup](./openclaw-backup/) | Backup and restore OpenClaw data with scheduling and rotation | `npx clawhub@latest install openclaw-backup` |

## openclaw-whisperer

Comprehensive troubleshooting suite for OpenClaw. Automated error diagnosis across 10 categories, auto-fix for 40+ common issues, smart skill recommendations from ClawHub, deep health checks, and interactive setup wizard.

```bash
python3 openclaw-whisperer/scripts/enhanced-doctor.py         # Full diagnostics
python3 openclaw-whisperer/scripts/error-fixer.py --auto-fix  # Auto-fix safe issues
python3 openclaw-whisperer/scripts/skill-recommender.py --auto-detect  # Skill recommendations
```

See [openclaw-whisperer/SKILL.md](./openclaw-whisperer/SKILL.md) for full documentation.

## skill-hub

Unified skill discovery, security vetting, and installation for OpenClaw. Searches 3000+ curated skills from ClawHub registry and awesome-openclaw-skills catalog. Scores credibility, detects prompt injection and malicious patterns, manages installations.

```bash
python3 skill-hub/scripts/skill-hub-search.py --query "spreadsheet"  # Search skills
python3 skill-hub/scripts/skill-hub-vet.py --slug google-sheets      # Security vet
python3 skill-hub/scripts/skill-hub-status.py                        # Status dashboard
```

See [skill-hub/SKILL.md](./skill-hub/SKILL.md) for full documentation.

## skill-vetting

Evaluate ClawHub skills for security risks and practical utility before installing. Automated scanner detects eval/exec, obfuscation, prompt injection, undocumented network calls. Includes decision matrix and manual review workflow.

```bash
python3 skill-vetting/scripts/scan.py /tmp/skill-inspect  # Scan downloaded skill
```

See [skill-vetting/SKILL.md](./skill-vetting/SKILL.md) for full documentation.

## openclaw-backup

Backup and restore OpenClaw configuration, credentials, and workspace. Daily cron scheduling, automatic 7-day rotation, selective archiving with proper exclusions.

```bash
./openclaw-backup/scripts/backup.sh              # Create backup
./openclaw-backup/scripts/backup.sh ~/my-backups  # Custom backup dir
```

See [openclaw-backup/SKILL.md](./openclaw-backup/SKILL.md) for full documentation.

## Requirements

- Python 3.8+
- OpenClaw installed and configured
- Dependencies: `pip install click rich requests beautifulsoup4`

## License

MIT License - See [LICENSE](./LICENSE) for details.
