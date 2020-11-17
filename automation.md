Operation Automation for ALTO
=============================

## Proposed paragraph

Best practice documentation and extension of ALTO for operation automation.
Operating an ALTO server can be complex, and the automation of the operations
of the ALTO services can be highly valuable. The operations of an ALTO server
includes decisions on the set of information resources (e.g., what metrics,
how they are divided into multiple entries) exposed in the information
resource directory (IRD), population (may be proactive and reactive) of the
content of the services (e.g., pull the backend, or trigger just-in-time
measurements), and aggregation/processing of the collected information to
give clients the proper response. Because of the dynamicity of network states
and application demands, the automation of the ALTO server operations
requires more inputs from applications. The working group will (1)
investigate the best practices in ALTO operations automation, including
interop/interfaces/protocols with routing systems and measurement tools; (2)
propose the new protocol extension for more application-aware information to
enable reactive measurement and computation.

## Basic Issue

- New complexity of operations
  - Practical operations of an ALTO server includes the complex workflow
  - New ALTO protocol extensions (e.g., the incremental update mechanism, cost
    calendar, unified properties, and path vector) introduce more complexity to
    operations
- Inefficient measurement and computation
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
- Define the new interface (service) between application and server to allow
  the application to subscribe demand and enable reactive measurement and
  computation:
  - interested E2E flows
  - constraints for flows

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
- IETF 110: initial draft for protocol extension
- IETF 112: best practice documentation
