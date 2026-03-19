---
title: Get Random Reachable Point In Radius
---

# Get Random Reachable Point In Radius

**Plugin:** StateTreeToolsCore
**Category:** AI|Navigation

Queries the navigation system for a random point on the navmesh that is within a given radius of a center position and is reachable by the navigation agent. If a valid point is found the task writes it to **Random Point** and succeeds immediately. If no reachable point is found the task fails.

---

## Configuration

### Center
The world-space origin of the search area.

### Radius
The maximum distance from Center to search for a reachable point. Default is `600`.

### Nav Data *(optional)*
A specific `ANavigationData` actor to query. Leave unbound to use the default navigation data for the world.

### Filter Class
A `UNavigationQueryFilter` subclass that controls which navigation areas are passable during the query. Leave empty to use the default filter.

### Random Point *(output)*
Receives the world-space location of the randomly selected reachable point when the query succeeds.

---

## Error Handling

This task does not inherit from `FStateTreeTools_TaskCommon` and therefore does not have an **Error Means Failure** toggle. If the navigation query fails (no reachable point found, or the navigation system is unavailable) the task returns **Failed**.

[← Back to Navigation](/tasks/navigation) · [← Back to home](/)
