# Collector Configurator Tool

<div align="center">
  
**An intuitive web-based tool for generating and editing OpenTelemetry Collector configuration files**

The _Collector Configuration Generator_ is an easy-to-use web interface for creating and editing OpenTelemetry Collector configuration files.

Try it out here: [grafana.github.io/collector-configurator/](https://grafana.github.io/collector-configurator/)

[Live Demo](https://grafana.github.io/collector-configurator/) | [Report Bug](https://github.com/grafana/collector-configurator/issues) | [Request Feature](https://github.com/grafana/collector-configurator/issues)

</div>

## Overview

The Collector Configurator is a user-friendly web interface designed to simplify the creation and management of OpenTelemetry Collector configuration files. Originally forked from the Grafana Agent Configurator, this tool has been adapted to work seamlessly with OpenTelemetry Collector pipelines, making it easier for DevOps engineers and SREs to configure observability pipelines without deep YAML expertise. [github](https://github.com/grafana/collector-configurator/blob/main/README.md)

## Features

- **Visual Configuration Builder** - Create complex collector configurations through an intuitive web interface
- **OpenTelemetry Native** - Full support for OTel Collector configuration structure including receivers, processors, exporters, and extensions [opentelemetry.website.cncfstack](https://opentelemetry.website.cncfstack.com/docs/collector/configuration/)
- **Real-time Validation** - Instant feedback on configuration syntax and structure
- **Export & Import** - Generate downloadable YAML configuration files and import existing configs for editing
- **Live Preview** - See your configuration YAML update in real-time as you make changes
- **No Installation Required** - Use the hosted version or run locally with minimal setup

## Use Cases

- **Quick Prototyping** - Rapidly test different collector configurations before deploying to production
- **Learning Tool** - Understand OpenTelemetry Collector configuration structure through visual exploration [opentelemetry.website.cncfstack](https://opentelemetry.website.cncfstack.com/docs/collector/configuration/)
- **Configuration Management** - Centralize and standardize collector configurations across your infrastructure
- **Troubleshooting** - Validate and debug existing collector configurations

## Getting Started

### Online Usage

Access the hosted version immediately at: **[grafana.github.io/collector-configurator](https://grafana.github.io/collector-configurator/)** [grafana](https://grafana.com/docs/opentelemetry/collector/)

### Local Development Setup

#### Prerequisites

- Node.js 18.x or higher
- npm package manager

#### Installation

```bash
# Clone the repository
git clone https://github.com/grafana/collector-configurator.git
cd collector-configurator

# Install dependencies
# Note: --force flag is required due to React dependency conflicts
npm install --force

# Start the development server
npm start
```

The application will be available at `http://localhost:3000`. [grafana](https://grafana.com/docs/opentelemetry/collector/)

#### Build for Production

```bash
# Create optimized production build
npm run-script build
```

The build artifacts will be generated in the `build/` directory. [github](https://github.com/grafana/collector-configurator/blob/main/.github/workflows/deploy.yaml)

## Architecture

This is a React-based single-page application that provides:

- **Frontend**: React application with form-based configuration builder
- **Configuration Engine**: Transforms UI inputs into valid OpenTelemetry Collector YAML
- **Conversion Endpoint**: Backend API for configuration validation and conversion [github](https://github.com/grafana/collector-configurator/blob/main/.github/workflows/deploy.yaml)

### Technology Stack

- **React** - Frontend framework
- **React Hook Form** - Form state management
- **Node.js** - Development environment
- **GitHub Pages** - Hosting platform for the live demo

## Configuration Structure

The tool supports the standard OpenTelemetry Collector configuration components: [opentelemetry](https://opentelemetry.io/docs/collector/configuration/)

| Component | Purpose |
|-----------|---------|
| **Receivers** | Define how telemetry data is received (OTLP, Prometheus, Jaeger, etc.) |
| **Processors** | Transform, filter, and enrich telemetry data |
| **Exporters** | Send processed data to backends (Grafana Cloud, Prometheus, Jaeger, etc.) |
| **Extensions** | Add capabilities like health checks, authentication, and diagnostics |
| **Service Pipelines** | Connect receivers, processors, and exporters into data flows |

## Deployment

The repository includes automated GitHub Actions workflow for continuous deployment to GitHub Pages: [github](https://github.com/grafana/collector-configurator/blob/main/.github/workflows/deploy.yaml)

- **Trigger**: Automatic deployment on push to `main` branch
- **Environment**: GitHub Pages with custom domain support
- **Build**: Production-optimized React build with environment variables

## Contributing

Contributions are welcome! Please feel free to submit issues or pull requests.

### Development Notes

- The project uses `npm ci --force` during CI/CD due to React Hook Form compatibility requirements with newer React versions [github](https://github.com/grafana/collector-configurator/blob/main/.github/workflows/deploy.yaml)
- Environment variables are configured via GitHub Secrets for Faro observability integration

## Related Projects

- [OpenTelemetry Collector](https://opentelemetry.io/docs/collector/) - The official OpenTelemetry Collector
- [Grafana Alloy](https://grafana.com/oss/alloy-opentelemetry-collector/) - Grafana's OpenTelemetry Collector distribution [grafana](https://grafana.com/oss/alloy-opentelemetry-collector/)
- [Grafana Fleet Management](https://grafana.com/docs/learning-journeys/fleet-mgt-monitor-health/) - Manage and monitor multiple collectors at scale

## License

This project is maintained by Grafana Labs. Check the repository for license details.

## Support

- **Issues**: Report bugs or request features via [GitHub Issues](https://github.com/grafana/collector-configurator/issues)
- **Documentation**: [OpenTelemetry Collector Documentation](https://opentelemetry.io/docs/collector/)
- **Community**: [Grafana Community Forums](https://community.grafana.com/)

***

**Built with ❤️ by Grafana Labs**

***

This README provides comprehensive documentation covering setup, features, architecture, and usage patterns. It's structured to help both beginners getting started with OpenTelemetry Collector configuration and experienced SREs looking for a productivity tool for managing collector configs across their infrastructure.
