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

## Docker Environment

Docker is provided through Docker Desktop on the Windows host and integrated with the Ubuntu WSL2 development environment.

Installed versions at initial setup:

- Docker Desktop: `4.91.0`
- Docker Engine: `29.8.0`
- Docker CLI: `29.8.0`
- Docker Compose: `v5.5.1`

Docker Desktop uses the WSL2 backend and is integrated with the `Ubuntu-26.04` distribution.

The Docker CLI is available inside Ubuntu at:

`/usr/bin/docker`

A separate Docker Engine was not installed inside Ubuntu. The Ubuntu Docker CLI communicates with the engine managed by Docker Desktop.

### Verification

The Docker setup was verified from Ubuntu using both client/server inspection and an actual container execution.

`docker version` confirmed communication between:

- the Linux Docker client running inside Ubuntu/WSL2; and
- Docker Engine running through Docker Desktop.

The first WSL session did not initially have the newly assigned `docker` group membership loaded. The Docker socket was owned by the `docker` group and the user was already registered as a member, so WSL was restarted to refresh the user session rather than changing socket permissions or installing another Docker service.

After the restart, the user session included the `docker` group and Docker Engine became accessible without `sudo`.

The engine was then verified with:

`docker run hello-world`

Docker successfully:

1. contacted the Docker daemon;
2. downloaded the `hello-world` image from Docker Hub;
3. created a container from the image;
4. executed the container; and
5. returned the expected `Hello from Docker!` output.

Running the command a second time reused the locally available image and successfully created another container.

No project-specific Docker configuration has been added to G64 at this stage. Dockerfiles, Compose configuration, and application container architecture will be introduced only if required by the later planning and architecture process.