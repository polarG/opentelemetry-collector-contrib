# Solarwinds APM Settings extension

<!-- status autogenerated section -->
| Status        |           |
| ------------- |-----------|
| Stability     | [development]  |
| Distributions | [] |
| Issues        | [![Open issues](https://img.shields.io/github/issues-search/open-telemetry/opentelemetry-collector-contrib?query=is%3Aissue%20is%3Aopen%20label%3Aextension%2Fsolarwindsapmsettings%20&label=open&color=orange&logo=opentelemetry)](https://github.com/open-telemetry/opentelemetry-collector-contrib/issues?q=is%3Aopen+is%3Aissue+label%3Aextension%2Fsolarwindsapmsettings) [![Closed issues](https://img.shields.io/github/issues-search/open-telemetry/opentelemetry-collector-contrib?query=is%3Aissue%20is%3Aclosed%20label%3Aextension%2Fsolarwindsapmsettings%20&label=closed&color=blue&logo=opentelemetry)](https://github.com/open-telemetry/opentelemetry-collector-contrib/issues?q=is%3Aclosed+is%3Aissue+label%3Aextension%2Fsolarwindsapmsettings) |
| Code coverage | [![codecov](https://codecov.io/github/open-telemetry/opentelemetry-collector-contrib/graph/main/badge.svg?component=extension_solarwindsapmsettings)](https://app.codecov.io/gh/open-telemetry/opentelemetry-collector-contrib/tree/main/?components%5B0%5D=extension_solarwindsapmsettings&displayType=list) |
| [Code Owners](https://github.com/open-telemetry/opentelemetry-collector-contrib/blob/main/CONTRIBUTING.md#becoming-a-code-owner)    | [@jerrytfleung](https://www.github.com/jerrytfleung), [@cheempz](https://www.github.com/cheempz) |

[development]: https://github.com/open-telemetry/opentelemetry-collector/blob/main/docs/component-stability.md#development
<!-- end autogenerated section -->

## Overview
The Solarwinds APM Settings extension gets Solarwinds APM specific settings from Solarwinds APM collector and `/tmp/solarwinds-apm-settings.json` periodically.

## Configuration

Example:

```yaml
extensions:
  solarwindsapmsettings:
    endpoint: "<endpoint>"
    key: "<token>:<name>"
    interval: 10s
```

### endpoint (Required)
The APM collector endpoint which this extension calls `getSettings`. See [SolarWinds Observability SaaS: Data centers and endpoint URIs](https://documentation.solarwinds.com/en/success_center/observability/content/system_requirements/endpoints.htm) for our APM collector endpoints. The endpoint is in format `<host>:<port>`.

### key (Required)
The service key in format `<token>:<name>` for `getSettings` from Solarwinds APM collector. See [SolarWinds Observability SaaS: Add a service](https://documentation.solarwinds.com/en/success_center/observability/content/configure/configure-services.htm) for configuring a service key.

### interval (Optional)
Periodic interval to get Solarwinds APM specific settings from Solarwinds APM collector.

Minimum value: `5s`

Maximum value: `60s`

Value that is outside the boundary will be bounded to either the minimum or maximum value.

Default: `10s`
