# Getting Started
# Installation & Getting Started with PeTTa

Efficient MeTTa implementation in Prolog.

---

***Prerequisites***

Before you can run PeTTa, make sure your system has the following:
### Dependencies
SWI-Prolog

### Operating System
- Linux, macOS, or Windows

### SWI-Prolog
- Version ≥ 9.x – the Prolog interpreter used to run PeTTa.
- [Download SWI-Prolog](https://www.swi-prolog.org/Download.html)
- Follow the installation instructions for your OS.

### Ubuntu/Debian/ WSL

```bash
sudo apt update
sudo apt install swi-prolog
```
### macOS
```bash 
brew install swi-prolog
```
### Git
- To clone the repository (if not already installed):

```bash
git --version

```

## Quick install
```bash
git clone https://github.com/patham9/PeTTa.git
cd PeTTa
```
#### Running PeTTa

#### PeTTa comes with a run script for executing .metta files.

```bash
time sh run.sh ./examples/minnars.metta
```


### To run the docs server locally (requires mkdocs installed)
```
mkdocs serve
```

#### tips
- Keep SWI-Prolog up-to-date; PeTTa relies on modern Prolog features.
- Use the examples folder to learn the syntax before writing new programs.
- Always run .metta files from the repository root to avoid path issues.
