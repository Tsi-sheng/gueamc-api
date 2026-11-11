# Gueamc API

> The public API contract for Gueamc server infrastructure.

## Project status

This repository is **public** and is maintained independently from the private Gueamc Core implementation.

The API is currently in the interface-design and initialization stage. No stable API release or production compatibility guarantee has been declared.

**License status:** This repository currently has no `LICENSE` file. Public repository visibility allows the source to be viewed but does not grant permission to copy, modify, redistribute, or use it beyond rights provided by applicable law. A license will be selected and added after ownership and dependency review.

## Project positioning

Gueamc API defines the public contracts exposed by the Gueamc infrastructure plugin. Gueamc Core implements these contracts and provides their runtime services.

Consumer plugins should compile against the API and must not depend on private Core implementation classes.

## Scope

The API may contain the following stable public contracts:

- Service interfaces and service lookup contracts;
- Plugin lifecycle and extension contracts where cross-plugin use is required;
- Events and listener contracts;
- Public data types, results, and exceptions;
- API and implementation compatibility metadata.

These are design boundaries, not a statement that every item has already been implemented.

## Dependency rules

- Gueamc Core implements Gueamc API.
- Consumer plugins depend on Gueamc API, not on Gueamc Core internals.
- Gueamc API must not depend on Gueamc Core.
- Gueamc API must not contain Oriri Tales-specific business models.
- Platform-specific types should be kept out of the API unless their use is explicitly required and documented.

The runtime packaging model, plugin load order, and exact server-version compatibility must be documented and tested before a stable release.

## Versioning and compatibility

Gueamc API and Gueamc Core are versioned independently.

Public contract changes require compatibility review and migration notes. Semantic Versioning is the intended versioning scheme once the first stable release is established:

- PATCH: compatible fixes;
- MINOR: backward-compatible additions;
- MAJOR: breaking contract changes.

Version numbers do not replace compile-time, integration, and runtime compatibility tests.

## Build and publication

The Gradle project structure and publication coordinates have not yet been initialized. No Maven artifact is currently promised or published.

Before publication, the project must establish:

- Java and Gradle toolchain baselines;
- Stable package namespace and Maven coordinates;
- API compatibility policy;
- License and dependency review;
- Release and artifact verification workflow.

## Maintenance

Gueamc API is a personal Gueamc project maintained by its owner. Consumer projects may propose API additions, but acceptance is based on general reuse value, stability, and long-term maintenance cost.

## Related project

- **Gueamc Core**: private implementation of this API.
- **OriSurge / Oriri Tales**: a consumer of Gueamc capabilities under a separate usage authorization.

