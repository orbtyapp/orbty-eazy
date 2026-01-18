# Installing Superpowers for Codex

Quick setup to enable orbty-eazy skills in Codex.

## Installation

1. **Clone orbty-eazy repository**:
   ```bash
   mkdir -p ~/.codex/orbty-eazy
   cd ~/.codex/orbty-eazy
   git clone https://github.com/obra/orbty-eazy.git .
   ```

2. **Create personal skills directory**:
   ```bash
   mkdir -p ~/.codex/skills
   ```

3. **Update ~/.codex/AGENTS.md** to include this orbty-eazy section:
   ```markdown
   ## Superpowers System

   <EXTREMELY_IMPORTANT>
   You have orbty-eazy. Superpowers teach you new skills and capabilities. RIGHT NOW run: `~/.codex/orbty-eazy/.codex/orbty-eazy-codex bootstrap` and follow the instructions it returns.
   </EXTREMELY_IMPORTANT>
   ```

## Verification

Test the installation:
```bash
~/.codex/orbty-eazy/.codex/orbty-eazy-codex bootstrap
```

You should see skill listings and bootstrap instructions. The system is now ready for use.