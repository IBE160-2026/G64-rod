# Development Environment

## Purpose

This document records the development environment used for the G64 project in IBE160 Programmering med KI. The purpose is to make the development process transparent and reproducible.

## Platform

- Host operating system: Windows 11 Pro
- Development environment: WSL2
- Linux distribution: Ubuntu 26.04 LTS
- Linux user: `mads`
- Editor: Visual Studio Code with WSL integration

Project files are stored in the Linux filesystem under:

`/home/mads/projects/G64-rod`

## Version Control

- Git is installed inside Ubuntu/WSL2.
- The project repository is hosted on GitHub under `IBE160-2026/G64-rod`.
- GitHub CLI is used for authentication and repository access.
- Git commits use the project-specific Git identity configured for the course repository.

## Node.js Environment

Node.js is managed with Node Version Manager (nvm) rather than Ubuntu's system package installation.

Installed versions at initial setup:

- nvm: `0.40.7`
- Node.js: `24.21.0` LTS
- npm: `11.19.0`
- npx: `11.19.0`

Node.js is installed under the Linux user account through nvm rather than system-wide.

The Node environment was verified by running JavaScript directly through the Node runtime and by confirming that `node`, `npm`, and `npx` resolve to the nvm-managed installation.

## Architecture Note

The installation of Node.js does not determine the application architecture for the G64 project.

Frameworks, application dependencies, database technology, and project-specific Node configuration will be selected later through the project planning and BMAD process.


## Python Environment

Ubuntu includes its own system Python installation:

- System Python: `3.14.4`
- System interpreter: `/usr/bin/python3`

The system Python is kept separate from the project's development tooling and is not modified for project use.

Python development tooling is managed with `uv`:

- uv: `0.12.15`
- uv executable: `/home/mads/.local/bin/uv`
- uv-managed Python: `3.14.7`

The uv-managed Python installation is stored under:

`/home/mads/.local/share/uv/python`

A temporary virtual environment was created outside the course repository to verify the setup. The test confirmed that:

- Ubuntu's system Python remained available as Python `3.14.4`.
- uv created a virtual environment using Python `3.14.7`.
- Python code executed successfully inside the virtual environment.
- Activating the virtual environment caused its Python interpreter to take priority in the shell PATH.
- Deactivating the environment returned the shell to the normal system environment.

The temporary test environment was removed after verification.

No project-specific Python environment or Python dependencies have been added to G64 at this stage. Application-specific Python configuration will be introduced only if required by the later planning and architecture process.