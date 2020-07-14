# WSL

## xdg-open in WSL
```bash
sudo apt update
sudo apt install ubuntu-wsl
sudo ln -s /usr/bin/wslview /usr/local/bin/xdg-open
```

## fix vim & tmux copy/paste
Options for [win32yank](https://github.com/equalsraf/win32yank):
- Create `/usr/local/bin/win32yank.exe` for vim to find
- Include `win32yank.exe` (located on windows) to path
- Link to xclip

**Or** use directly inside `init.vim` / `init.lua`
```vim
if executable('/mnt/c/Windows/System32/win32yank.exe')
    let g:clipboard = {
    \ 'name': '/mnt/c/Windows/System32/win32yank.exe',
    \ 'copy': {
    \    '+': '/mnt/c/Windows/System32/win32yank.exe -i --crlf',
    \    '*': '/mnt/c/Windows/System32/win32yank.exe -i --crlf',
    \  },
    \ 'paste': {
    \    '+': '/mnt/c/Windows/System32/win32yank.exe -o --lf',
    \    '*': '/mnt/c/Windows/System32/win32yank.exe -o --lf',
    \ },
    \ 'cache_enabled': 1,
    \ }
else
    echo "Failed to locate win32yank.exe: /mnt/c/Windows/System32/win32yank.exe"
endif
```
