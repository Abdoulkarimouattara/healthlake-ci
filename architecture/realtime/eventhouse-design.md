# Eventhouse Design

## Overview

Eventhouse provides the operational data store for streaming healthcare events.

It enables near real-time querying of incoming telemetry while maintaining a scalable environment optimized for event analytics.

---

# Event Storage

Incoming telemetry events are organized to support rapid analytical queries without impacting historical analytical workloads.

Typical event categories include:

* Patient vital signs.
* Device connectivity.
* Equipment status.
* Clinical monitoring events.

---

# Operational Analytics

Eventhouse enables healthcare teams to:

* Monitor live patient conditions.
* Analyze device activity.
* Detect operational anomalies.
* Investigate recent events.

Unlike the Lakehouse, which stores long-term historical data, Eventhouse is optimized for operational intelligence and low-latency event analysis.

---

# Platform Integration

Eventhouse works together with Eventstream and KQL to create a complete real-time analytics pipeline while remaining integrated with the broader Microsoft Fabric ecosystem.

---

# Design Principle

Separate operational event analytics from historical business analytics while maintaining a unified data platform.
