![Documentation](https://img.shields.io/badge/api-reference-blue.svg)
![Chat](https://img.shields.io/badge/chat-on%20forums-blue)
![PRs welcome!](https://img.shields.io/badge/PRs-welcome!-success)

<img src="https://opensearch.org/assets/brand/SVG/Logo/opensearch_logo_default.svg" height="64px"/>

- [OpenSearch Telemetry Collector](#opensearch-telemetry-collector)
- [Highlights](#highlights)
- [Documentation](#documentation)
- [Contributing](#contributing)
- [Code of Conduct](#code-of-conduct)
- [Security](#security)
- [License](#license)
- [Copyright](#copyright)

# OpenSearch Telemetry Collector

Colloquially Tracking/Traceability, Distributed Tracing is the ability to trace a request end-to-end in the system to get a complete view of the request execution, With respect to OpenSearch: From Coordinator, fanning to all the respective nodes with primary/replica shard and aggregating the result back on the coordinator. The supported use-cases will include Bad Query Debugging, Critical Path Analysis and A/B Testing.

The Distributed Tracing system will consist of 2 major components: Tracing Framework(details at [#6750](https://github.com/opensearch-project/OpenSearch/issues/6750)) and Telemetry Collector. The Tracing Framework will instrument and collect (node)local and (cluster-wide)distributed traces for OpenSearch search, index workloads and background jobs etc. The OpenSearch Telemetry Collector will offer a vendor-agnostic implementation to read, process and export telemetry (Initially trace, later Performance Analyzer metrics as well) data to stores like Prometheus, Jaeger, AWS XRay etc.

The OpenSearch Collector will be a distribution of [Otel Collector](https://opentelemetry.io/docs/collector/), curated for OpenSearch specific use-case. The Collector Agent will be designed as a Golang Binary, running as a side-car process on the same node to ensure process level resource isolation and no over-the-network cost. It will run as a custom user/RBAC role with limited privileged access to network, specific Disk Locations etc.

## Contributing

See [CONTRIBUTING](CONTRIBUTING.md#security-issue-notifications) for more information.

## Code of Conduct

This project has adopted the [Amazon Open Source Code of Conduct](CODE_OF_CONDUCT.md). For more information see the [Code of Conduct FAQ](https://aws.github.io/code-of-conduct-faq), or contact [opensource-codeofconduct@amazon.com](mailto:opensource-codeofconduct@amazon.com) with any additional questions or comments.

## Security

If you discover a potential security issue in this project we ask that you notify AWS/Amazon Security via our [vulnerability reporting page](http://aws.amazon.com/security/vulnerability-reporting/). Please do **not** create a public GitHub issue.

## License

This project is licensed under the Apache-2.0 License.

## Copyright

Copyright OpenSearch Contributors. See [NOTICE](NOTICE) for details.
