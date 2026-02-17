# KOMPAS-3D SDK Documentation

This repository contains the source documentation for the KOMPAS-3D SDK, built using [Diplodoc](https://github.com/diplodoc-platform/diplodoc) - a documentation platform by Yandex.

## Overview

The KOMPAS-3D SDK (Software Development Kit) provides developers with tools and APIs to create applications that integrate with KOMPAS-3D, a popular CAD (Computer-Aided Design) software developed by ASCON.

This documentation includes:

- **API Reference** - Detailed documentation for KOMPAS API
- **Constants** - Enumerations and constants used in the SDK
- **Base API** - Core API objects and interfaces
- **Applications API** - Application-level API for creating KOMPAS extensions

## Project Structure

```
kompas-sdk-help/
├── .github/
│   └── workflows/
│       └── static.yml          # GitHub Actions workflow for deployment
├── .yfm                        # YFM configuration (Diplodoc settings)
├── _assets/                    # Static assets (images, logos)
└── src/
    ├── en/                     # English documentation
    └── ru/                     # Russian documentation
        ├── constants/          # Enumerations and constants
        ├── kompas-api-base/    # Base API documentation
        ├── kompas-api-apps/    # Applications API documentation
        │   └── documents/      # Document-related APIs
        │       └── 2d-documents/  # 2D document APIs
        │           └── view/   # View and rendering APIs
        ├── help.md             # Help and contact information
        ├── index.yaml          # Main index configuration
        ├── rules.md            # Platform rules and guidelines
        └── toc.yaml            # Table of contents configuration
```

## Languages

The documentation is available in multiple languages:

- **Russian (ru)** - Primary language
- **English (en)** - Secondary language

The language configuration is defined in the [`.yfm`](.yfm) file.

## Building the Documentation

### Prerequisites

- Node.js 18 or later
- npm or yarn

### Local Development

To build the documentation locally, you need to use the Diplodoc CLI. Install it globally:

```bash
npm install -g @diplodoc/client
```

Then build the documentation:

```bash
# Build from src directory to build
yfm build -i ./src -o ./build
```

For development:

```bash
npx http-server ./build -p 5005
```

This will start a local development server (typically at http://localhost:5005.

### Build Output

The build process generates static HTML files in the output directory (default: `./build`), which can be deployed to any static hosting service.

## Contributing

Contributions to improve the documentation are welcome! Here are some guidelines:

### Adding New Documentation

1. Create or edit Markdown (`.md`) files in the appropriate language directory under `src/`
2. Update the table of contents in `toc.yaml` to include new pages
3. Test your changes locally using `diplodoc start`

### Documentation Format

The documentation uses Markdown with YFM (YAML Front Matter) for metadata:

```yaml
---
title: Page Title
description: Page description
---
```

### API Documentation

API documentation should follow the existing patterns in the repository:
- Include method signatures
- Provide parameter descriptions
- Add usage examples where appropriate

## Configuration

### .yfm File

The `.yfm` file contains global configuration:

```yaml
allowHTML: true          # Allow HTML in Markdown files
lang: 'ru'              # Default language
langs: ['ru', 'en']     # Supported languages
pdf:
  - enabled: true       # Enable PDF generation
docs-viewer:
  - logo-options:
      - src: URL to logo
```

### Table of Contents

The `toc.yaml` file defines the navigation structure. Each entry can be:
- A simple link (`href`)
- A directory with nested items (`items`)
- An included file (`include`)

## License

This documentation is provided for educational and reference purposes. For information about the KOMPAS-3D SDK licensing, please visit the [official ASCON website](https://ascon.ru).

## Resources

- [KOMPAS-3D Official Website](https://kompas3d.ru)
- [ASCON Official Website](https://ascon.ru)
- [Diplodoc Documentation](https://diplodoc.com)
- [KOMPAS SDK Documentation](https://help.ascon.ru/KOMPAS_SDK/)

## Support

For questions about the KOMPAS-3D SDK:
- Visit the [official documentation](https://help.ascon.ru/KOMPAS_SDK/)
- Contact ASCON support
