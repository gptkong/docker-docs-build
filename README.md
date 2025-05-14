# Docker Documentation Build

This repository contains Dockerfiles and related resources for building and running documentation websites for various projects. Each subdirectory corresponds to a specific project and contains the necessary Dockerfile and other resources.

## Directory Structure

- `react-cn-docs/`
  - Contains the Dockerfile for building the React Chinese documentation site.
- `react-flow/`
  - Contains the Dockerfile for building the React Flow documentation site.
- `react-hook-form/`
  - Contains the Dockerfile for building the React Hook Form documentation site.
- `shadcn-ui-docs/`
  - Contains the Dockerfile for building the ShadCN UI documentation site.
- `tailwindcss-docs/`
  - Contains the Dockerfile for building the TailwindCSS documentation site.
- `tanstack/`
  - Contains the Dockerfile for building the TanStack documentation site.

## Usage

Each directory contains a `Dockerfile` that can be used to build and run the corresponding documentation site. Below are the general steps to use the Dockerfiles:

1. Navigate to the directory of the project you want to build.
2. Build the Docker image:
   ```powershell
   docker build -t <image-name> .
   ```
3. Run the Docker container:
   ```powershell
   docker run -p <host-port>:<container-port> <image-name>
   ```

Replace `<image-name>`, `<host-port>`, and `<container-port>` with appropriate values.

## Example

To build and run the TailwindCSS documentation site:

```powershell
cd tailwindcss-docs

docker build -t tailwindcss-docs .

docker run -p 3000:3000 tailwindcss-docs
```

## Notes

- Ensure Docker is installed and running on your system.
- Some projects may require additional dependencies or configurations. Refer to the respective `Dockerfile` for details.

## License

This repository is licensed under the MIT License. See the LICENSE file for more details.
