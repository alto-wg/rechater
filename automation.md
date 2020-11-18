Operation Automation for ALTO
=============================

## Proposed paragraph

Best practice documentation and extension of ALTO for operation automation.
Operating an ALTO server can be complex, and the automation of the operations
of the ALTO services can be highly valuable. Although the working group has
proposed a best practice document (i.e., RFC7971) to talk about deployment
considerations including the operation automation, newer ALTO protocol
extensions (e.g., the incremental update mechanism, cost calendar, unified
properties, and path vector) and newer use cases (e.g., ZSM closed-loop
automation, mobile edge computing) require additional considerations
including but not limited to decisions on the set of information resources
(e.g., what metrics, how they are divided into multiple entries) exposed in
the information resource directory (IRD), population (may be proactive and
reactive) of the content of the services (e.g., pull the backend, or trigger
just-in-time measurements), and aggregation/processing of the collected
information to give clients the proper response. Furthermore, newer ALTO
services may populate the response dynamically and reactively, that requests
more communications with applications to better predict/decide which
low-level information (e.g., INT) should be collected/measured, and which
intermediate information (e.g., end-to-end path cache) should be precomputed.
The working group will (1) investigate the best practices in ALTO operations
automation to support newer ALTO protocol extensions and use cases; (2)
propose a new protocol extension to allow applications to subscribe demands
including interested flows and related resources.

## Basic Issue

- Complexity of operations on new extensions and new use cases
  - Practical operations of an ALTO server includes the complex workflow
  - New ALTO protocol extensions (e.g., the incremental update mechanism,
    cost calendar, unified properties, and path vector) require new
    architectural and deployment considerations
  - New use cases (e.g., ZSM closed-loop automation, mobile edge computing)
    require new operation integrations with different systems
- Reactive measurement and computation
  - ALTO information resource may be populated reactively, which requests
    more communications with applications to predict/decide which low-level
    information (e.g., INT) should be collected/measured, and which intermediate
    information (e.g., end-to-end path cache) should be precomputed

## Potential solution(s)

- Investigate best practices (extending RFC7971) including:
  - Automatic IRD generation
  - ALTO information resources population from information collected by existing routing
    systems and measurement tools (e.g., TEDB, LSPDB, SNMP)
  - Reactive ALTO information resources update
  - Aggregation of different information sources
  - Considerations about intermediate abstraction (e.g., history, path cache)
- Define a new interface (service) between the application and server to allow
  the application to subscribe demands and enable reactive measurement and
  computation:
  - Interested E2E flows
  - Constraints for flows
  - Potential metrics

## Remaining issues to be addressed

- How to reactively populate on-demand ALTO information resources (e.g., path
  vectors) based on client queries
- Flows that applications are interested in may change because of dynamic
  network state
  - e.g., applications are only interested in the endpoints attached to the
    specific PoP (Point of Presence)
- Constraints for interested flows may be correlated
  - e.g., filter all sources whose total upload bandwidth are higher than the
    threshold

## Who will work on it

- Luis/Jensen/Kai
- Any other interested people

## Potential milestones (1-2 years)

- IETF 109: problem statement
- IETF 110: initial draft for the protocol extension
- IETF 112: best practice documentation
