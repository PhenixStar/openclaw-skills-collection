# OpenClaw Doctor Pro

Comprehensive diagnostic, error-fixing, and skill recommendation tool for OpenClaw.

## What is OpenClaw Doctor Pro?

OpenClaw Doctor Pro is an advanced troubleshooting suite for [OpenClaw](https://github.com/openclaw/openclaw) - a self-hosted AI gateway that connects messaging apps (WhatsApp, Telegram, Discord, Slack, Signal) to AI agents.

**Key Features:**
- 🔍 Automated error diagnosis across 10 error categories
- 🔧 Auto-fix capabilities for 40+ common issues
- 💡 Smart skill recommendations from ClawHub (5,700+ skills)
- 📊 Deep health checks and performance monitoring
- 📚 Comprehensive reference documentation
- 🎯 Interactive setup wizard for first-time users

## What's New in v1.1.0

- **🤝 Complementary Skills** - Discover skills that work together (10 skill relationships)
- **🔔 Diagnostic Hooks** - GitHub/Slack/Discord integration for error notifications (9 hook configs)
- **📈 Recovery Tracking** - Track fix execution history and success rates
- **🎯 Smart Scoring** - Enhanced recommendations with complementary skill bonus scoring
- **🎨 Rich Display** - Improved CLI panels and formatting for suggestions
- **📦 7 New Modules** - complementary_skills, diagnostic_integrations, recovery_integrations, notification_hooks, recommendation_scoring, fix_execution_tracker, error_fixer_display

## Quick Start

### Installation

```bash
# Install dependencies
pip install click rich requests beautifulsoup4

# Run diagnostic
python3 scripts/enhanced-doctor.py

# Fix errors automatically
python3 scripts/error-fixer.py --fix-all-safe

# Get skill recommendations
python3 scripts/skill-recommender.py --auto-detect
```

### First-Time Setup

```bash
# Interactive setup wizard
python3 scripts/setup-wizard.py

# Or check prerequisites only
python3 scripts/setup-wizard.py --check-only
```

## Tools Overview

### Enhanced Doctor
`python3 scripts/enhanced-doctor.py [--deep] [--json]` - Extended diagnostics

### Error Fixer (v1.1.0 features)
```bash
python3 scripts/error-fixer.py --error 401          # Diagnose (triggers hooks)
python3 scripts/error-fixer.py --auto-fix           # Auto-fix safe issues (tracks history)
python3 scripts/error-fixer.py --show-history       # View fix execution history
python3 scripts/error-fixer.py --test-hooks         # Test GitHub/Slack/Discord hooks
```

### Skill Recommender (v1.1.0 features)
```bash
python3 scripts/skill-recommender.py --auto-detect              # Auto-detect (complementary metadata)
python3 scripts/skill-recommender.py --complementary-for SKILL  # View complementary skills
python3 scripts/skill-recommender.py --channel whatsapp         # Channel recommendations
```

### Self-Updater
`python3 scripts/self-updater.py [--check] [--update] [--skills-only]` - Keep caches current

### Setup Wizard
`python3 scripts/setup-wizard.py [--check-only]` - Interactive first-time setup

## Documentation

**References:** `references/` contains 12 comprehensive guides (error-catalog, auth-errors, rate-limiting, gateway, channels, sandbox, config, installation, diagnostic-commands, clawhub-integration, auto-fix-capabilities, troubleshooting-workflow)

**Templates:** `templates/` contains error-report and recommendation-report formats

**Data:** `data/` contains error-patterns, skills-cache, complementary-skills (v1.1.0), integration-hooks (v1.1.0), fix-execution-history (v1.1.0)

## Error Categories

10 categories: Authentication, Rate Limiting, Gateway, Channels, Sandbox, Configuration, Installation, Plugins, Skills, System

## Auto-Fix Safety Levels

- ✅ **Safe** - Fully automated (timeout increase, retry enable, config type conversion)
- ⚠️ **Moderate** - Optional confirmation (kill port process, permissions fix)
- 🔴 **Risky** - Explicit confirmation (token regeneration, Docker start)
- ❌ **Manual** - Guidance only

See [auto-fix-capabilities.md](references/auto-fix-capabilities.md) for complete list.

## Common Workflows

**Gateway Won't Start:** `enhanced-doctor.py` → `error-fixer.py --fix-all-safe` → check port → fix EADDRINUSE

**Channel Issues:** `openclaw channels status` → `error-fixer.py --category channel` → test channel → see references/channel-errors.md

**Rate Limits:** `openclaw quota show` → `error-fixer.py --error 429 --auto-fix` → enable fallback

**Find Skills:** `skill-recommender.py --auto-detect` → view complementary → install → check updates

**Track Fixes (v1.1.0):** `error-fixer.py --show-history` → `--test-hooks` → auto-fix with recovery tracking

## ClawHub Integration

5,700+ skills: AI/ML, Automation, Utilities, Integrations, Communication, Data

**Popular:** image-generator-pro, pdf-toolkit, workflow-builder, google-workspace, auto-responder

See [clawhub-integration.md](references/clawhub-integration.md)

## Project Structure

```
openclaw-doctor-pro/
├── SKILL.md                                  # ClawHub manifest (v1.1.0)
├── README.md                                 # This file
├── scripts/
│   ├── enhanced-doctor.py                   # Extended diagnostics
│   ├── error-fixer.py                       # Auto-fix errors
│   ├── skill-recommender.py                 # Skill recommendations
│   ├── self-updater.py                      # Update tool
│   └── setup-wizard.py                      # First-time setup
├── modules/                                  # 27 Python modules (all <200 lines)
│   ├── complementary_skills.py              # NEW: Complementary skill scoring
│   ├── diagnostic_integrations.py           # NEW: Diagnostic hook triggers
│   ├── recovery_integrations.py             # NEW: Fix tracking + recovery
│   ├── notification_hooks.py                # NEW: GitHub/Slack/Discord hooks
│   ├── recommendation_scoring.py            # NEW: Extracted scoring logic
│   ├── fix_execution_tracker.py             # NEW: Execution metadata
│   ├── error_fixer_display.py               # NEW: Rich display helpers
│   ├── recommendation_engine.py             # ENHANCED: Bonus scoring
│   ├── fix_engine.py                        # ENHANCED: Hook triggers
│   ├── clawhub_cache.py                     # ENHANCED: Complementary metadata
│   └── ...                                  # 17 other modules
├── references/
│   ├── error-catalog.md                     # Error index
│   ├── authentication-errors.md             # Auth issues
│   ├── rate-limiting-errors.md              # Rate limits
│   ├── gateway-errors.md                    # Gateway issues
│   ├── channel-errors.md                    # Channel issues
│   ├── sandbox-errors.md                    # Sandbox issues
│   ├── configuration-errors.md              # Config issues
│   ├── installation-errors.md               # Install issues
│   ├── diagnostic-commands.md               # CLI reference
│   ├── clawhub-integration.md               # Skill management
│   ├── auto-fix-capabilities.md             # Fix reference
│   └── troubleshooting-workflow.md          # Decision trees
├── templates/
│   ├── error-report.md                      # Error report template
│   └── recommendation-report.md             # Recommendation template
├── data/
│   ├── error-patterns.json                  # Error definitions
│   ├── skills-cache.json                    # ClawHub cache
│   ├── complementary-skills.json            # NEW: 10 skill relationships
│   ├── integration-hooks.json               # NEW: 9 hook configs
│   └── fix-execution-history.json           # NEW: Fix tracking
└── cache/
    └── skill-recommendations.json           # Cached recommendations
```

**Stats:** 27 Python modules, 3,567 lines total, all under 200 lines each.

## Requirements & Installation

**Requirements:** Python 3.8+, OpenClaw, Dependencies: click, rich, requests, beautifulsoup4

```bash
git clone https://github.com/PhenixStar/openclaw-doctor-pro.git
cd openclaw-doctor-pro
pip install click rich requests beautifulsoup4
python3 scripts/setup-wizard.py
```

## Contributing

Contributions welcome: error patterns, auto-fix recipes, skill recommendations, platform support, documentation

## License

MIT License - See LICENSE file for details.

## Support & Acknowledgments

**Support:** [GitHub Issues](https://github.com/openclaw/openclaw/issues) | [Docs](https://docs.openclaw.io) | [Discord](https://discord.gg/openclaw)

**Thanks:** OpenClaw core team, ClawHub contributors, community testers

---

**OpenClaw Doctor Pro v1.1.0** - Because every gateway needs a doctor 🏥
