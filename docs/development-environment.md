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