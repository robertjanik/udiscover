# udiscover - Universal Discovery of services

This project aims to establish a standardized list of services, each with a definition that includes a description and the configuration of the service exposed on a global or local network by a server.
The idea originated from investigating APIs provided by various AI vendors as well as tools that can be run on a local network as daemons exposing open‑source or proprietary AI models. I thought it would be useful if every server offered a single source describing all its AI services for example in a JSON file that applications, AI agents, or other systems could query to discover:

* What type of AI service the server provides
* How the service is configured
* What authentication (if any) is required

Examples of possible queries:

* Query a server from Company A for a Large Language Model (LLM) service so an app can send prompts and receive responses.
* Query a server from Company B to learn about its Convolutional Neural Network (CNN) model used for image‑classification tasks.
* Query a server from Company C for the configuration of a generative‑AI service that creates images from natural‑language descriptions.

Instead of manually reading documentation or SDKs, an application/agent could simply request this discovery file, much like how a Swagger/OpenAPI specification describes backend APIs.

To make this work seamlessly, we need a way to:

1. Discover and identify the services a given server provides.
2. Learn how each API can be configured.
3. Determine required authentication (or whether anonymous access is allowed).
4. Know which input data formats are supported and how to configure API to accept that format. 
5. Know which input data formats are supported and how to configure API to generate output in selected format.

While exploring this concept, I realized that a single source of truth could cover not only AI services but also well‑known domains such as Email, Calendar, Contacts, and other proprietary or niche services. This led to the idea of Universal Discovery.

## Proposed Implementation
The discovery document would be a simple JSON file named udiscovery.json. It could be placed on a server and exposed via one of the following URLs:

* https://server.com/udiscovery.json
* https://server.com/.well-known/udiscovery.json

(The latter follows the widely used “/.well‑known/” convention - see https://en.wikipedia.org/wiki/Well-known_URI)

## Call for Collaboration
In this GitHub project I have added an initial udiscovery.json, generated with the help of AI. However, maintaining a comprehensive catalog of existing services and defining a robust standard requires more resources than I can provide alone.

If you work for a large organization or are otherwise interested in shaping, expanding, and stewarding Universal Discovery, please consider contributing or taking ownership of this effort. Together we can create an open, extensible specification that benefits the entire ecosystem of Universal Discovery.
