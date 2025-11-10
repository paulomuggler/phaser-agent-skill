# Phaser Agent Skill for Claude Code

This repository contains a Claude Code skill for the **Phaser 3 HTML5 Game Framework**, designed to help developers build games using Phaser with TypeScript and JavaScript.

## What is This?

This is a [Claude Code skill](https://www.anthropic.com/news/skills) that provides comprehensive knowledge about Phaser 3, including:

- Core concepts (Scenes, Game Objects, Physics)
- TypeScript integration and type definitions
- Input handling (keyboard, mouse, touch, gamepad)
- Animation and tweens
- Audio management
- Camera systems
- Asset loading
- Common patterns and best practices

## Using This Skill

### Option 1: Download Pre-built Skill

The pre-built skill is available as `phaser.zip` in this repository.

1. Download `phaser.zip`
2. Go to [https://claude.ai/skills](https://claude.ai/skills)
3. Click "Upload Skill"
4. Select the downloaded `phaser.zip` file
5. Start using Claude Code with Phaser knowledge!

### Option 2: Build from Source

If you want to customize or rebuild the skill:

```bash
# Clone this repository
git clone https://github.com/paulomuggler/phaser-agent-skill.git
cd phaser-agent-skill

# Initialize the Skill_Seekers submodule
git submodule update --init --recursive

# Set up Python environment
cd Skill_Seekers
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\\Scripts\\activate
pip install -r requirements.txt

# The skill files are already generated in Skill_Seekers/output/phaser/
# To package it again:
python3 cli/package_skill.py output/phaser/

# The packaged skill will be at: output/phaser.zip
```

## What's Inside

### SKILL.md
Comprehensive guide covering:
- Quick start templates
- Core concepts (Scenes, Game Objects, Physics)
- TypeScript configuration
- Common patterns
- Performance tips
- API quick reference

### Reference Documentation
- **getting_started.md**: Installation and first game setup
- **phaser_readme.md**: Official Phaser README with features and resources
- **changelog.md**: Version history and updates
- **index.md**: Navigation guide to all reference materials

## How This Skill Was Built

Due to Phaser's documentation sites blocking automated scraping, this skill was manually crafted using:

1. **Local Phaser Repository**: Cloned from https://github.com/phaserjs/phaser
2. **Official Documentation**: Information from https://docs.phaser.io
3. **TypeScript Definitions**: From the Phaser npm package
4. **Community Resources**: Tutorials and examples from https://phaser.io/learn

The skill leverages the [Skill_Seekers](https://github.com/yusufkaraaslan/Skill_Seekers) framework for packaging and structure.

## Regenerating/Updating the Skill

If Phaser releases a new version and you want to update the skill:

### Method 1: Update from Local Repository

```bash
# Update the Phaser repository
cd phaser-repo
git pull origin main
cd ..

# Update skill references
cp phaser-repo/README.md Skill_Seekers/output/phaser/references/phaser_readme.md
cp phaser-repo/CHANGELOG.md Skill_Seekers/output/phaser/references/changelog.md

# Edit SKILL.md to reflect new features/changes
nano Skill_Seekers/output/phaser/SKILL.md

# Repackage
cd Skill_Seekers
source venv/bin/activate
python3 cli/package_skill.py output/phaser/
cp output/phaser.zip ../
```

### Method 2: Automated Scraping (if documentation becomes accessible)

If Phaser's documentation sites become scraper-friendly in the future:

```bash
cd Skill_Seekers
source venv/bin/activate

# Try one of the configs:
python3 cli/doc_scraper.py --config ../configs/phaser.json --enhance-local
# or
python3 cli/doc_scraper.py --config ../configs/phaser_accessible.json --enhance-local

# Package the result
python3 cli/package_skill.py output/phaser/
```

## Configuration Files

This repository includes several configuration attempts for automated scraping:

- **configs/phaser.json**: Primary docs.phaser.io config (currently blocked)
- **configs/phaser_accessible.json**: Alternative photonstorm docs (currently blocked)
- **configs/phaser_tutorials.json**: Phaser.io tutorials config
- **configs/phaser_unified.json**: Combined docs + GitHub repository

## Resources

### Phaser Resources
- **Official Site**: https://phaser.io
- **Documentation**: https://docs.phaser.io
- **Examples**: https://labs.phaser.io (2000+ examples)
- **Tutorials**: https://phaser.io/learn
- **GitHub**: https://github.com/phaserjs/phaser
- **Discord**: https://discord.gg/phaser

### Skill_Seekers Framework
- **GitHub**: https://github.com/yusufkaraaslan/Skill_Seekers
- **Documentation**: See Skill_Seekers/README.md

## Contributing

To improve this skill:

1. Fork this repository
2. Make your changes to the skill files in `Skill_Seekers/output/phaser/`
3. Rebuild: `python3 cli/package_skill.py output/phaser/`
4. Test the new skill in Claude Code
5. Submit a pull request

Suggested improvements:
- Add more code examples
- Update for latest Phaser version
- Add framework integration guides (React, Vue, etc.)
- Include performance optimization tips
- Add debugging and testing guidance

## License

This skill documentation is provided as-is for use with Claude Code. Phaser itself is released under the MIT License. See the official Phaser repository for licensing details.

## Credits

- **Phaser Framework**: Created and maintained by [Phaser Studio Inc](https://phaser.io) and the Phaser community
- **Skill_Seekers**: Created by [Yusuf Karaaslan](https://github.com/yusufkaraaslan)
- **This Skill**: Compiled and packaged using Skill_Seekers framework

---

**Need help?** Open an issue or check the [Phaser Discord](https://discord.gg/phaser) for game development questions.
