# Komune.io Trace Codebase

This repository contains the codebase and documentation for Komune.io Trace, a suite of microservices focused on managing certification processes and environmental project/asset tracking.

The project is composed of two main modules:

* **trace-cccev**: Facilitates managing certification processes based on the CCCEV vocabulary.

* **trace-registry**: A system for managing environmental projects and assets like carbon credits.

## Modules

### trace-cccev

The `trace-cccev` project facilitates managing **certification processes**. It allows defining complex *Requirements* based on the standard CCCEV vocabulary, including associated *InformationConcepts* (specific data points) and needed *Evidence* (proofs). The system uses a **Neo4j graph database** to store these interconnected elements and provides an **F2 API** to create certifications and track their fulfillment by adding evidence and values.

For detailed documentation on `trace-cccev`, please refer to the [trace-cccev Tutorial](trace-cccev/index.md).

### trace-registry

The `trace-registry` project is a sophisticated digital system for managing and tracking information about **projects**, particularly *environmental initiatives*, and their associated **assets** like *carbon credits or certificates*. It achieves this by organizing data into **Catalogues** (akin to library sections) and **Datasets** (specific information items), using standardized metadata formats like *DCAT/DCAT-AP* for discoverability. The system's architecture relies on **S2 Event Sourcing** to record every change as an *immutable event*, providing a full audit trail and enabling the reconstruction of current states for entities like Catalogues and Projects. Backend functionalities are primarily exposed through **F2 Function-Based APIs**, which handle specific *commands* (to perform actions) and *queries* (to request information) in an event-driven manner. For managing compliance and verification, the project incorporates the **CCCEV (Core Criterion and Core Evidence Vocabulary)** standard, allowing the definition of *Requirements* and the linking of *Evidences* to demonstrate fulfillment. The entire application, composed of various microservices, is built, tested, and deployed using **automated infrastructure** leveraging Docker, GitHub Actions, and Makefiles.

For detailed documentation on `trace-registry`, please refer to the [trace-registry Tutorial](trace-registry/index.md).

## License

This project is licensed under the Apache License, Version 2.0. See the [LICENSE](LICENSE) file for details.
