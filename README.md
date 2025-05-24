### 🧰 DevContainer Setup for Raylib 5

This repository sets up a fully containerized development environment for working on Raylib-related assignments using modern tooling. 

I built this in my free time because every student deserves a modern, intuitive coding setup—something that often isn’t given much thought. It’s my attempt to make getting started easier for anyone, whether you’ve struggled before or haven’t yet seen what’s possible.

---
### ✅ Why use this?
  
  Using this DevContainer gives you:  
- 🚀 **Quick setup** – no need to fiddle with dependencies or IDE settings.
- 🧼 **Clean and consistent environment** – it works the same on every machine.
- 🔎 **Real-time feedback** – thanks to `clangd` and `errorlens`, you get inline diagnostics *as you type*, without waiting for a full build.
  
---
### 🛠️ Prerequisites
  
  Before you begin, make sure these tools are installed:  
- [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- [Visual Studio Code](https://code.visualstudio.com/)
- [Git](https://git-scm.com/)
  
---
### 🧪 Step-by-Step Setup
- #### 1. Clone the Repository
  
  ```
  git clone https://github.com/johannes-p/Raylib5-Devcontainer
  cd Raylib5-DevContainer
  ```
  
---
- #### 2. Open in VS Code
	    
    From the cloned folder run:  
	    
    ```
    code .
    ```
	    
    VS Code will open and prompt you to install the "Dev Containers"-Extension followed by a prompt to reopen the folder in a DevContainer. Click **“Reopen in Container”** and let it do its thing. This might take a minute the first time as Docker sets everything up.  
	    
> [!NOTE]  
    Once inside the container, you're in a fully isolated dev environment with all tools preconfigured.  
	    
---
- #### 3. Clone the Raylib Wrapper
  
  As a student you'll probably need to download the Raylib-wrapper provided by the university for your coursework, clone the github repository or download and copy the folder into the top-level directory:  
  
  ```
  git clone <repo-url>
  ```
  
---
- #### 4. Add the Tile Assets
  
  Copy the required assets folder "`tiles/`" into the build directory.  
  This ensures your assets are available to your compiled programs at runtime.  
  
---
- #### 5. (Optional) Offline DevContainer Workaround
  
  If you’re working offline or behind a network that causes trouble with container pulls, you can add this line to your hosts file (located at `C:\Windows\System32\drivers\etc\hosts`):  
  
  ```
  127.0.0.1    mcr.microsoft.com
  ```
  
  This prevents VS Code from stalling when it tries to reach the container registry. ([related issue](https://github.com/microsoft/vscode-remote-release/issues/10173)) Just remember to remove the line if you want to connect to the registry again.  

---  
### 🎉 You’re Ready!  
Once everything is set up, you can compile, run, and debug your projects right from inside the container.

---

### 🐞 Troubleshooting

* #### GLFW Error: Missing DISPLAY Variable

  If you encounter the following error when trying to run your program inside the DevContainer:

  ```
  WARNING: GLFW: ERROR: 65550 Description: X11: The DISPLAY environment variable is missing
  WARNING: GLFW: Failed to initialize GLFW
  ```

  This usually happens due to issues with the WSL2 integration and the container's display environment.

  Run the following command *outside* of VS Code in a regular Windows Command Prompt or PowerShell to uninstall the problematic Docker Desktop WSL integration:

  ```
  wslconfig /u docker-desktop
  ```

  Then restart Docker Desktop and reopen your DevContainer.

---

### ⚠️ Known Limitations

While this DevContainer setup brings many benefits like consistency and modern tooling, there are some trade-offs to keep in mind:

- #### Performance

  There is noticeable latency and sluggishness when running Raylib programs inside the container compared to native Windows setups like Code::Blocks. The containerized environment, combined with WSL2 and graphics forwarding, adds overhead that can - and likely will - impact responsiveness and frame rates.

---
### 👨‍💻 Why Not Just Use Code::Blocks?
  
  While **Code::Blocks** is a classic tool that’s familiar to many, modern setups like this offer:  
- ✨ **Real-time error feedback** with `clangd`, so you can catch issues *while* writing code.
- 🧪 **Isolated environments**, so your system stays clean and you won’t accidentally “break” your setup.
- 🧰 **Modern tooling** that aligns with what you'll see in real-world development workflows.
  
  That said, use what works for you—but as a positive side effect, you’ll pick up valuable experience with a flexible, widely adopted IDE.
  
---