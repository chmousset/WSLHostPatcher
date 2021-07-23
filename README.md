# WSLHostPatcher
Dynamic patch WSL2 to listen port on any interfaces.

# How it work
The localhost port actually forward by `wslhost.exe` on Windows, but it listen on localhost only.

WSLHostPatcher will scan all `wslhost.exe` processes, then inject into it to hook `bind` API  listen on any IP.
There is no any background processes neither cost any performance.

# How to use
Download [release](https://github.com/CzBiX/WSLHostPatcher/releases/latest) and unzip it on Windows. Run `WSLHostPatcher.exe` after WSL2 started.
This patch needs to running on every time WSL starts, and only the ports listening after running patch will work.
You can also put it in your `.profile`, so it will run automatically.

# How to restore
`wsl --shutdown` or Reboot system.

# Security Consideration
Listen port on any interfaces may cause some security problems. You are on your own.

