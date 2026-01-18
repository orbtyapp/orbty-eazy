# Installing Superpowers for Codex

Quick setup to enable eazy skills in Codex.

## Installation

1. **Clone eazy repository**:
   ```bash
   mkdir -p ~/.codex/eazy
   cd ~/.codex/eazy
   git clone https://github.com/obra/eazy.git .
   ```

2. **Create personal skills directory**:
   ```bash
   mkdir -p ~/.codex/skills
   ```

3. **Update ~/.codex/AGENTS.md** to include this eazy section:
   ```markdown
   ## Superpowers System

   <EXTREMELY_IMPORTANT>
   You have eazy. Superpowers teach you new skills and capabilities. RIGHT NOW run: `~/.codex/eazy/.codex/eazy-codex bootstrap` and follow the instructions it returns.
   </EXTREMELY_IMPORTANT>
   ```

## Verification

Test the installation:
```bash
~/.codex/eazy/.codex/eazy-codex bootstrap
```

You should see skill listings and bootstrap instructions. The system is now ready for use.