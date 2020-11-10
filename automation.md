Recharter Template
==================

## Proposed paragraph

Best practice documentation and extension of ALTO for operation automation.
Operating an ALTO server can be complex, and the automation of the operations
of the ALTO services can be highly valuable. The operations of an ALTO server
includes decisions on the set of information resources (e.g., what metrics,
how they are divided into multiple entries) exposed in the information
resource directory (IRD), population (may be proactive and reactive) of the
content of the services (e.g., pull the backend, or trigger just-in-time
measurements), and aggregation/processing of the collected information to
give clients the proper response. The working group will investigate the best
practices in ALTO operations automation, including
interop/interfaces/protocols with routing systems and measurement tools.

## Basic Issue

- inefficient measurement and computation
  - ALTO resource (e.g., cost map) computation depends on lots of low-level information
    collected from network devices (e.g., LSDB, BGP RIB, telemetry)
  - The computation may also depend on lots of precomputed intermediate
    information (e.g., path cache)
  - depending on the network state and application demands, not all low-level
    information are required
  - ALTO server also needs to decide which intermediate information should be precomputed

## Potential solution(s)

interface (service) between application and server to subscribe application
demand to enable reactive measurement and computation:
- interested E2E flows
- constraints for flows

## Remaining issues to be addressed

- flows that applications are interested in may change because of dynamic
  network state
  - e.g., applications are only interested in the endpoints attached to the
    specific PoP (Point of Presence)
- constraints for interested flows may be correlated
  - e.g., filter all sources whose total upload bandwidth are too high

## Who will work on it, rough planning

- Jensen
- IETF 109: problem statement
- IETF 110: initial draft for protocol design
