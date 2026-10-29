# CTF Scripts

Helper scripts I use for CTF binary-exploitation and reverse-engineering challenges.

| Script | Purpose |
|---|---|
| `pwn_template.py` | pwntools exploit skeleton. Run it locally, under GDB in a tmux split (`GDB`), or against a remote target (`REMOTE host port`). The ELF and libc are loaded automatically. |
| `auto_ghidra.py` | Imports a binary into a Ghidra project and runs headless analysis, then opens it in the Ghidra GUI. Based on [liba2k's script](https://gist.github.com/liba2k/d522b4f20632c4581af728b286028f8f). |

## Usage
```bash
# exploit template
cp pwn_template.py exploit.py   # set PATH_TO_BINARY
python3 exploit.py              # local
python3 exploit.py GDB          # debug in a tmux split
python3 exploit.py REMOTE chal.example.com 1337

# auto-analyze a binary in Ghidra (set GHIDRA_PATH in the script)
python3 auto_ghidra.py ./challenge
```

Requires: `pwntools`, `click`, Ghidra, tmux.

The Ghidra FID database generator that used to live here is now in [Ghidra_Scripts](https://github.com/nyxysecurity/Ghidra_Scripts).
