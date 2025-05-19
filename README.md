# 🚀 Kompile

A minimalist C compiler wrapper with auto-execution that enforces strict compilation flags by default. Perfect for quick prototyping and learning!

## ✨ Features

- 🔥 Auto-executes programs after successful compilation
- ⚡ Supports both `gcc` and `clang` (with `-l` flag)
- 🛡️ Strict compiler flags enabled by default
- 📁 Configurable output directory
- 🧠 Simple KEY=VALUE config file
- 🐧 Pure Bash - no dependencies

## 📦 Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/kompile.git
   cd kompile
   ```

2. Make it executable:
   ```bash
   chmod +x kompile
   ```

3. (Optional) Add to your PATH:
   ```bash
   sudo ln -s $(pwd)/kompile /usr/local/bin/kompile
   ```

## 🛠️ Configuration

Create a config file at either:
- `./kompile.conf` (project-local)
- `~/.config/kompile.conf` (user-global)

Example config (`~/.config/kompile.conf`):
```ini
# Default compiler (gcc or clang)
DEFAULT_COMPILER=gcc

# Common flags (comma-separated)
COMMON_FLAGS=-std=c99,-pedantic,-Wall,-Wextra,-Werror,-O2,-g

# Compiler-specific flags
CC_FLAGS=-flto
CLANG_FLAGS=-Weverything

# Default behavior
DEFAULT_EXECUTE=1
OUTPUT_DIR=bin
```

## 🚀 Usage

Basic compilation and execution:
```bash
kompile program.c
```

Compile-only (no execution):
```bash
kompile -c program.c
```

Use clang instead of default compiler:
```bash
kompile -l program.c
```

Specify output name:
```bash
kompile program.c myapp
```

## 🌟 Example Workflow

1. Create `hello.c`:
   ```c
   #include <stdio.h>
   
   int main() {
       printf("Hello from kompile!\n");
       return 0;
   }
   ```

2. Compile and run:
   ```bash
   kompile hello.c
   ```
   Output:
   ```
   Compiling hello.c → hello using cc...
   ✅ Compilation successful!
   🚀 Executing hello...
   ----------------------------------------
   Hello from kompile!
   ```

## 📝 License

This project is licensed under the GNU General Public License v3.0 - see the [LICENSE](https://raw.githubusercontent.com/jocerfranquiz/kompile/refs/heads/main/LICENSE) file for details.

---

💡 **Pro Tip**: Add `kompile` to your shell aliases for even faster development!

