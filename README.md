# 🔄 RepoSync

> A lightweight, native Windows utility that transforms local folders into live-synced GitHub repositories using minimal system resources.

RepoSync provides a seamless "cloud drive" experience for GitHub without the bloat of heavy background services. By utilizing a clean system tray interface to generate highly optimized batch scripts, RepoSync hands off the actual syncing work directly to the native Windows Task Scheduler. This ensures zero friction, zero manual terminal commands, and an absolute minimal memory footprint.

## ✨ Features
* **System Tray Interface:** A distraction-free UI that lives quietly in your taskbar. Open it only when you need to adjust settings or configure a new repository.
* **Native Automation:** Instead of running a heavy, continuous background loop, the app dynamically generates a targeted `.bat` script and registers it with Windows Task Scheduler to execute invisibly.
* **"Start at Boot" Integration:** Easily toggle startup behavior directly from the interface so your folders sync automatically the moment your OS loads.
* **Highly Resource Efficient:** By leaning entirely on native OS scheduling and batch execution, the active application consumes virtually zero background memory.

## 🏗️ Architecture
1. **The Controller (UI):** A lightweight graphical interface used to configure the target local directory, the remote GitHub repository, and desired sync intervals.
2. **The Generator:** Based on your configuration, the application dynamically generates a custom batch (`.bat`) script containing the necessary Git automation commands (`add`, `commit`, `push`).
3. **The Executor:** The application seamlessly interfaces with the Windows OS to register the generated script with Task Scheduler, allowing it to run silently in the background.

## 🛠️ Tech Stack
* **Frontend/UI:** [Insert your chosen framework here, e.g., Python Tkinter/CustomTkinter, C# WPF, or Electron]
* **Core Logic:** File I/O for `.bat` script generation
* **System Integration:** Git CLI, Windows Task Scheduler, Windows Registry (for boot management)
