# SONiC Top-N Interface Traffic — Application Prep

## 1) Project Goal
Build a SONiC CLI feature that shows the top N interfaces by current traffic using existing interface counters.

## 2) Problem Understanding
SONiC exposes per-interface counters, but operators currently lack a quick way to identify which interfaces are carrying the highest traffic. Manually scanning counters is inefficient in large deployments.

## 3) Expected Features
- Show top 5 interfaces by traffic (RX + TX)
- Configurable sampling interval
- JSON output option
- Minimal performance overhead
- Read counters from COUNTERS_DB
- Integrate into SONiC CLI

## 4) My Current Understanding
### Inputs
- Interface RX bytes / packets counters
- Interface TX bytes / packets counters
- Sampling interval

### Processing
- Read counters at time t1
- Wait for interval
- Read counters at time t2
- Compute delta
- Convert delta to rate
- Sort interfaces by throughput
- Display top N

### Outputs
- Human-readable CLI table
- Optional JSON output

## 5) Things I Need To Learn
- What is SONiC?
- Where SONiC CLI commands are implemented
- What COUNTERS_DB looks like
- How interface counters are stored / accessed
- How to add JSON output in sonic-utilities

## 6) Possible Implementation Plan
1. Add a new CLI command in sonic-utilities
2. Read interface counters from COUNTERS_DB
3. Sample twice over configurable interval
4. Compute RX/TX deltas and derive throughput
5. Rank interfaces by total traffic
6. Display top N
7. Add JSON output option
8. Add tests and validate formatting

## 7) Questions / Doubts
- Which file should this CLI command go into?
- How is COUNTERS_DB accessed in sonic-utilities?
- Is there an existing command that already reads interface counters?
- What is the preferred CLI output format in SONiC?

## 8) My Relevant Background
- Python / C++ / Java / Go
- Backend / systems project experience
- Linux / Git / GitHub
- Concurrent key-value backend project

## 9) Application Draft
(To be filled later)
