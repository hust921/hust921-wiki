#!/bin/bash
if command -v python2 > /dev/null; then
    xdg-open 'http://localhost:8000' &
    python2 -m SimpleHTTPServer 8000
elif command -v python3 > /dev/null; then
    xdg-open 'http://localhost:8000' &
    python3 -m http.server 8000
else
    echo -e "[\e[91mERROR\e[39m] Python2 and Python3 not available..."
    exit 99
fi
