# ESP32 MicroPython Bakefile

Bakefile with scripts to make ESP32 MicroPython development more effective. No special IDE or editor is needed. 
Only Bash and Python 3. 

Just write you code and let the bake to do the rest. 

## Installation

1. Clone this repo
2. Create Python virtualenv the way you prefer (optional)
3. install picocom (optional for `bake repl` command)
4. `pip install -r requirements.txt`
5. `cp .ampy.example .ampy`
6. adjust port and baudrate in `.ampy` if you need
 
## Usage

`bake minify <file>` minifies the Python source file

`bake upload <file> [<file> [<file> ...]]` minifies and upload given Python files to ESP32's micropython filesystem

`bake flash_clean` clears whole flash memory of ESP32

`bake flash_python` uploads micropython interpreter from given binary (downloadable from https://micropython.org/download/esp32/)

`bake repl` connects to esp32's micropython prompt via serial port (requires picocom)

`bake clean` removes the `out/` folder with all minified python sources and hex files

All commands except `bake minify` check if esp32 board is connected. If it is not available, they won't execute the upload.

All files created by scripts are stored in `out/` folder.
