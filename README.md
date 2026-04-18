# Non-Human Livestream

A comprehensive project for creating and managing AI-powered, non-human livestream content. This repository integrates character management, AI generation workflows, code automation, and documentation to produce intelligent virtual livestream experiences.

---

## 🎯 Overview

**Non-Human Livestream** combines cutting-edge AI tools (ComfyUI, Suno, language models) with organized workflows and character management to generate engaging virtual livestream content. The project maintains clear separation between character definitions, generation workflows, code automation, and documentation.

---

## 📁 Project Structure

\\\
Non-human-Livestream/
├── README.md                    # Project overview and quick start
├── tuan-tuan-red-panda.yaml    # Project configuration
│
├── Characters/                  # Character definitions
│   ├── Fennie.yaml             # Character profile
│   ├── Johnny.yaml             # Character profile
│   └── Tuan Tuan.yaml          # Character profile
│
├── workflow/                    # AI generation & execution workflows
│   ├── DAILY_WORKFLOW.md       # Daily routine and process
│   └── [ComfyUI configs, prompts, execution steps]
│
├── code/                        # Scripts, automations, and configurations
│   └── [Python scripts, APIs, integrations]
│
├── docs/                        # Documentation and process records
│   └── [Reflections, progress logs, technical notes]
│
├── presentation/               # Presentations and exports
│   └── [PPT, PDF, demo materials]
│
└── assets/                      # Generated and source materials
    └── [Images, audio, models, media files]
\\\

---

## 🎭 Characters

Character definitions are stored in \Characters/\ with YAML files defining personality, voice, appearance, and behavior parameters.

- **Fennie** - [Character profile](Characters/Fennie.yaml)
- **Johnny** - [Character profile](Characters/Johnny.yaml)
- **Tuan Tuan** - [Character profile](Characters/Tuan%20Tuan.yaml)

---

## 🚀 Quick Start

### 1. Check Your Memory & Identity
\\\ash
# Review your daily workflow
cat workflow/DAILY_WORKFLOW.md
\\\

### 2. Review Project Configuration
\\\ash
# Understand project settings
cat tuan-tuan-red-panda.yaml
\\\

### 3. Explore Characters
\\\ash
# View character definitions
ls Characters/
cat Characters/[Character].yaml
\\\

### 4. Set Up Environment (if using code)
\\\ash
# Navigate to code directory
cd code/

# Create virtual environment (Python)
python -m venv venv
source venv/Scripts/activate  # Windows: venv\Scripts\activate

# Install dependencies
pip install -r requirements.txt
\\\

---

## 🔧 Tools & Capabilities

### AI Generation
- **ComfyUI** - Image/video generation and processing
- **Suno** - Music and audio creation
- **Language Models** - Content generation and character dialogue

### Development
- **Python** - Scripting and automation
- **Web APIs** - Integration and data fetching
- **Workflow Automation** - Task orchestration

### Workflow Management
- **Sub-agents** - Parallel task execution for heavy lifting
- **Daily Routines** - Consistent process for content generation
- **Version Control** - Git-based project management

---

## 📋 Daily Workflow

Follow the **[Daily Workflow Guide](workflow/DAILY_WORKFLOW.md)** for:

1. **Morning Routine** - Review SOUL.md and IDENTITY.md
2. **Task Planning** - Identify daily objectives
3. **Tool Initiation** - Start ComfyUI renders, Suno generations
4. **Parallel Work** - Execute code tasks while tools process
5. **Sub-agent Dispatch** - Spin up agents for heavy-lifting
6. **Daily Logging** - Track progress and learnings
7. **Evening Review** - Update logs and plan tomorrow

---

## 💡 Working Process

### Before Starting
- [ ] Review \workflow/DAILY_WORKFLOW.md\
- [ ] Check character profiles in \Characters/\
- [ ] Review project configuration in \	uan-tuan-red-panda.yaml\

### During Development
- **Document Progress** - Log in \docs/\ as you work
- **Generate Assets** - Output to \ssets/\ or subdirectories
- **Store Code** - Keep scripts centralized in \code/\
- **Track Workflows** - Update workflow configs in \workflow/\

### Content Generation
1. Define requirements in character YAML or \docs/\
2. Prepare workflow/prompts in \workflow/\
3. Execute using appropriate tool (ComfyUI, Suno, Python)
4. Store outputs in \ssets/\
5. Document process in \docs/\

---

## 📚 Key Resources

- **[Daily Workflow](workflow/DAILY_WORKFLOW.md)** - Process and routine guide
- **[Character Definitions](Characters/)** - Virtual character profiles
- **[Project Configuration](tuan-tuan-red-panda.yaml)** - Project settings
- **[Documentation](docs/)** - Process records and learnings

---

## 🎬 Workflow Examples

### Image Generation (ComfyUI)
1. Prepare prompt in \workflow/\
2. Configure ComfyUI settings
3. Execute generation process
4. Review and export to \ssets/\

### Audio Generation (Suno)
1. Define character voice and style
2. Create lyrics/prompt
3. Queue generation
4. Download and store in \ssets/audio/\

### Code Automation
1. Write script in \code/\
2. Test in isolation
3. Integrate with workflows
4. Document in \docs/\

---

## 📝 Logging & Documentation

Maintain clear records:
- **Daily Logs** - \docs/daily-logs/\ with date-stamped entries
- **Learning Log** - \docs/learnings.md\ for insights
- **Process Notes** - Technical documentation in \docs/\

---

## 🔄 Version Control

This project uses Git. Key practices:
- Commit working changes regularly
- Use meaningful commit messages
- Keep generated assets out of frequent commits
- Document major milestones in \docs/\

---

## ⚙️ Configuration

Edit \	uan-tuan-red-panda.yaml\ to manage:
- Project metadata
- API keys and credentials
- Tool configurations
- Character defaults
- Output settings

---

## 🤝 Contributing

1. Review character profiles and project goals
2. Check \workflow/DAILY_WORKFLOW.md\ for current process
3. Create feature branches for new capabilities
4. Document changes in \docs/\
5. Update relevant workflow configs

---

## 📞 Support & Resources

For detailed workflows and processes, see:
- [Daily Workflow Guide](workflow/DAILY_WORKFLOW.md)
- [Character Documentation](Characters/)
- [Process Records](docs/)

---

**Last Updated**: April 18, 2026  
**Version**: 1.0
