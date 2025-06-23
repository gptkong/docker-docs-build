# Docker Documentation Build

> 适用于纯内网(无互联网)开发时的文档部署,其中tanstack部分代码进行过地址魔改

## Directory Structure

- `react-cn-docs/`
  - Contains the Dockerfile for building the React Chinese documentation site.
  - GitHub Repository: [React Chinese Docs](https://github.com/reactjs/zh-hans.react.dev)
- `react-flow/`
  - Contains the Dockerfile for building the React Flow documentation site.
  - GitHub Repository: [React Flow](https://github.com/xyflow/web)
- `react-hook-form/`
  - Contains the Dockerfile for building the React Hook Form documentation site.
  - GitHub Repository: [React Hook Form Docs](https://github.com/react-hook-form/documentation)
- `shadcn-ui-docs/`
  - Contains the Dockerfile for building the ShadCN UI documentation site.
  - GitHub Repository: [ShadCN UI](https://github.com/shadcn-ui/ui)
- `tailwindcss-docs/`
  - Contains the Dockerfile for building the TailwindCSS documentation site.
  - GitHub Repository: [TailwindCSS Docs](https://github.com/tailwindlabs/tailwindcss.com)
- `tanstack/`
  - Contains the Dockerfile for building the TanStack documentation site.
  - GitHub Repository: [TanStack](https://github.com/tanstack/tanstack.com)
- `lucide-icon-docs/`
  - Contains the Dockerfile for building the Lucide Icon documentation site.
  - GitHub Repository: [Lucide Icons](https://github.com/lucide-icons/lucide)
- `vitejs/`
  - Contains the Dockerfile for building the Vite Chinese documentation site.
  - GitHub Repository: [Vite Chinese Docs](https://github.com/vitejs/docs-cn)

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
