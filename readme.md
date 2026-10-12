# Awesome Aerospike [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> Distributed NoSQL database built for predictable sub-millisecond access at scale.

[Aerospike](https://aerospike.com) keeps its index in memory and its data on flash, which is how it serves millions of operations per second from a cluster small enough to reason about. That design shows up everywhere in its tooling: the cluster is self-managing, the operational surface is unusually small, and most of what you need is a handful of very good command-line tools.

This list collects what actually exists around it — the official clients, the community ones, the operational tooling, and the places to learn.

## Contents

- [Official](#official)
- [Clients](#clients)
- [Object Mappers and Framework Integrations](#object-mappers-and-framework-integrations)
- [Tools](#tools)
  - [Command Line](#command-line)
  - [Backup and Restore](#backup-and-restore)
  - [Benchmarking and Certification](#benchmarking-and-certification)
  - [Desktop](#desktop)
- [Deployment](#deployment)
  - [Kubernetes](#kubernetes)
  - [Containers and Provisioning](#containers-and-provisioning)
- [Monitoring](#monitoring)
- [Connectors and Integrations](#connectors-and-integrations)
- [Learning](#learning)

## Official

- [Aerospike Database](https://github.com/aerospike/aerospike-server) - The database server itself, written in C.
- [Documentation](https://aerospike.com/docs/) - Reference for the server, the clients and the tools.
- [Developer Docs](https://aerospike.com/docs/develop/) - Data modelling, expressions, transactions and the query language.
- [Architecture Guide](https://aerospike.com/docs/database/learn/architecture/) - How the hybrid memory model, clustering and cross-datacenter replication work.
- [Community Forum](https://discuss.aerospike.com/) - Where questions about the server and the clients get answered.
- [Blog](https://aerospike.com/blog/) - Release notes, benchmarks and engineering write-ups.
- [Community Hub](https://aerospike.com/community/) - Editions, licensing and how the open-source parts fit together.

## Clients

- [C](https://github.com/aerospike/aerospike-client-c) - The reference implementation; several other clients wrap it.
- [C#](https://github.com/aerospike/aerospike-client-csharp) - Official .NET client.
- [Clojure](https://github.com/AppsFlyer/aerospike-clj) - Community client with an idiomatic asynchronous API.
- [Go](https://github.com/aerospike/aerospike-client-go) - Pure Go, no cgo dependency.
- [Java](https://github.com/aerospike/aerospike-client-java) - Official Java client.
- [Java Reactive](https://github.com/aerospike/aerospike-client-java-reactive) - Reactive Streams interfaces over the Java client.
- [Lua](https://github.com/aerospike-community/client-lua) - Community client, separate from the server-side Lua UDF support.
- [Node.js](https://github.com/aerospike/aerospike-client-nodejs) - Official Node.js client, a native addon over the C client.
- [PHP 8](https://github.com/aerospike/php-client) - Current official PHP client, written in Rust.
- [Python](https://github.com/aerospike/aerospike-client-python) - Official Python client.
- [Ruby](https://github.com/aerospike-community/aerospike-client-ruby) - Community-maintained pure Ruby client.
- [Rust](https://github.com/aerospike/aerospike-client-rust) - Official Rust client.
- [JDBC](https://github.com/aerospike/aerospike-jdbc) - Minimalist JDBC driver, enough for SQL-shaped tooling.

## Object Mappers and Framework Integrations

- [Spring Data Aerospike](https://github.com/aerospike/spring-data-aerospike) - Repositories, templates and query derivation for Spring applications.
- [Spring Data Starters](https://github.com/aerospike/spring-data-aerospike-starters) - Spring Boot starters for the above.
- [Java Object Mapper](https://github.com/aerospike/java-object-mapper) - Annotation-driven mapping of POJOs to records.
- [Java Document API](https://github.com/aerospike-community/aerospike-document-lib) - JSONPath-style access to documents stored in maps and lists.
- [Python Document API](https://github.com/aerospike/document-lib-python) - The same idea for the Python client.
- [Django Plugin](https://github.com/aerospike-community/aerospike-django-plugin) - Django integration.
- [Express Session Store](https://github.com/aerospike-community/aerospike-session-store-expressjs) - Session storage for Express applications.
- [Expression DSL for Java](https://github.com/aerospike/aerospike-expression-lang-java) - Builds filter expressions from a readable DSL.

## Tools

### Command Line

- [AQL](https://aerospike.com/docs/database/tools/aql) - The SQL-like query shell; the fastest way to look at data.
- [asadm](https://github.com/aerospike/aerospike-admin) - Cluster administration and live statistics from a terminal.
- [Tools Reference](https://aerospike.com/docs/database/tools/) - Everything shipped in the tools package, in one place.
- [Info Commands](https://aerospike.com/docs/database/reference/info) - The raw info protocol that the tools are built on.

### Backup and Restore

- [asbackup and asrestore](https://github.com/aerospike/aerospike-tools-backup) - The standard backup and restore utilities.
- [Backup Service](https://github.com/aerospike/aerospike-backup-service) - Runs scheduled backups as a service, with an HTTP API.
- [absctl](https://github.com/aerospike/absctl) - Command-line control for the backup service.
- [backup-go](https://github.com/aerospike/backup-go) - Go library for embedding backup and restore in your own tooling.
- [asmt](https://github.com/aerospike/asmt) - Backs up and restores shared-memory indexes, for fast restarts.
- [Data Loader](https://github.com/aerospike-community/aerospike-loader) - Bulk loads CSV and JSON into a cluster.
- [Tools Validation](https://github.com/aerospike/aerospike-tools-validation) - Checks records for corruption before a restore.

### Benchmarking and Certification

- [ACT](https://github.com/aerospike/act) - Certifies whether a given SSD can sustain a real Aerospike workload.
- [asbench](https://github.com/aerospike/aerospike-benchmark) - Throughput and latency benchmarks against a live cluster.
- [asmalloc](https://github.com/aerospike/asmalloc) - Memory allocation tracking, for diagnosing server memory use.

### Desktop

- [Sutido](https://sutido.com) - Windows desktop client for Aerospike alongside MongoDB, PostgreSQL, SQL Server and ClickHouse, with an AQL editor and SSH tunnelling.
- [LINQPad Driver](https://github.com/aerospike-community/aerospike-linqpad-driver) - Query a cluster with LINQ from LINQPad.
- [Eclipse Tools](https://github.com/aerospike-community/eclipse-tools) - Eclipse plugins for browsing namespaces and running queries.

## Deployment

### Kubernetes

- [Kubernetes Operator](https://github.com/aerospike/aerospike-kubernetes-operator) - The supported way to run a cluster on Kubernetes.
- [Helm Charts](https://github.com/aerospike/aerospike-kubernetes) - Charts for the server and the surrounding services.
- [Management Library](https://github.com/aerospike/aerospike-management-lib) - The operations library the operator is built on.

### Containers and Provisioning

- [Server Images](https://github.com/aerospike/aerospike-server.docker) - Dockerfiles behind the official server image.
- [Docker Hub](https://hub.docker.com/_/aerospike) - The published server image.
- [Tools Image](https://github.com/aerospike/aerospike-tools.docker) - AQL, asadm and the backup tools in a container.
- [AeroLab](https://github.com/aerospike/aerolab) - Spins up throwaway clusters on Docker, AWS and GCP in one command.
- [Ansible Roles](https://github.com/aerospike-community/aerospike-ansible) - One-touch cluster setup on AWS.
- [Vault Plugin](https://github.com/aerospike-community/vault-plugin-database-aerospike) - Dynamic credentials for Aerospike through HashiCorp Vault.

## Monitoring

- [Prometheus Exporter](https://github.com/aerospike/aerospike-prometheus-exporter) - The official exporter for server and namespace metrics.
- [Monitoring Stack](https://github.com/aerospike/aerospike-monitoring) - Grafana dashboards and alert rules to go with it.
- [Graphite Integration](https://github.com/aerospike-community/aerospike-graphite) - Ships metrics to Graphite.
- [collectd Plugin](https://github.com/aerospike-community/aerospike-collectd) - Metrics through collectd.
- [Nagios Integration](https://github.com/aerospike-community/aerospike-nagios) - Checks for Nagios-based monitoring.

## Connectors and Integrations

- [Aerospike Connect](https://aerospike.com/docs/connectors) - The supported connectors for Kafka, Pulsar, Spark, Elasticsearch and JMS.
- [Inbound SDK](https://github.com/aerospike/aerospike-connect-inbound-sdk) - Write custom transforms for the inbound connectors.
- [Aerospike Graph](https://github.com/aerospike/aerospike-graph-service) - Apache TinkerPop-compliant graph database on top of Aerospike.
- [Graph Examples](https://github.com/aerospike/aerospike-graph) - Scripts and notebooks for getting started with Graph.
- [JanusGraph Backend](https://github.com/PlaytikaOSS/aerospike-janusgraph-storage-backend) - Aerospike as a JanusGraph storage backend.
- [Hadoop Connector](https://github.com/aerospike-community/aerospike-hadoop) - Reads and writes Aerospike data from MapReduce jobs.
- [Storm Connectors](https://github.com/aerospike-community/storm-aerospike) - Spouts and bolts for Apache Storm.
- [Trino Image](https://github.com/aerospike/trino-aerospike.docker) - Trino packaged with the Aerospike connector.

## Learning

- [Developer Notebooks](https://github.com/aerospike/aerospike-dev-notebooks.docker) - Jupyter notebooks with a server, client and tools in one image.
- [Sample Applications](https://github.com/aerospike-examples/aerospike-sample-applications) - Small end-to-end examples across several languages.
- [Student Workbook](https://github.com/aerospike-edu/student-workbook) - Lab exercises from the official training courses.
- [Spring Data Demo](https://github.com/aerospike/spring-data-aerospike-demo) - A worked Spring Boot application.
- [Resources](https://aerospike.com/resources/) - White papers, benchmarks and case studies.
- [Installation Guide](https://aerospike.com/docs/database/install/) - Getting a first cluster running.

## Contributing

Contributions are welcome. Read the [contribution guidelines](contributing.md) first.

## Footnotes

Five entries that were on this list are archived or have not been touched in
years. They are in [unmaintained.md](unmaintained.md) rather than deleted:
several are still the only thing of their kind, and knowing that something
exists but is abandoned beats not finding it at all.
