..
   ****************************************************************************
    pgRouting Website
    Copyright(c) pgRouting Contributors

    This documentation is licensed under a Creative Commons Attribution-Share
    Alike 3.0 License: https://creativecommons.org/licenses/by-sa/3.0/
   ****************************************************************************

.. _rfc-03:

RFC 03: [done] Implementation of "All-pairs shortest path" algorithm
===============================================================================

.. list-table::
   :widths: 15 85

   * - Date:
     - 2010/11/22
   * - Author:
     - Daniel Kastl
   * - Contact:
     - daniel at georepublic.de
   * - Last Edited:
     - 2013/06/09
   * - Status:
     - Implemented (v2.0.0)

Overview
********************************************************************************

The all-pairs shortest path problem aims to compute the shortest path from each
vertex v to every other u. Using standard single-source algorithms, you can
expect to get a naive implementation of O(n^3) if you use Dijkstra for example
-- i.e. running a O(n^2) process n times. Likewise, if you use the Bellman-Ford-
Moore algorithm on a dense graph, it'll take about O(n^4), but handle negative
arc-lengths too.

Storing all the paths explicitly can be very memory expensive indeed, as you
need one spanning tree for each vertex. This is often impractical in terms of
memory consumption, so these are usually considered as all-pairs shortest
distance problems, which aim to find just the distance from each to each node to
another.

The result of this operation is an n * n matrix, which stores estimated
distances to the each node. This has many problems when the matrix gets too big,
as the algorithm will scale very poorly.

[Source: https://ai-depot.com/BotNavigation/Path-AllPairs.html]


Implementation Details
********************************************************************************

There are two important algorithms that solve "All-pairs shortest path":

* Floyd-Warshall algorithm (https://en.wikipedia.org/wiki/Floyd%E2%80%93Warshall_algorithm)
* Johnson's algorithm (https://en.wikipedia.org/wiki/Johnson's_algorithm)

At least one of them should be considered, if possible both of them.


Backwards Compatibilty Issues
********************************************************************************

Are not expected


Documentation
********************************************************************************

Required.


Ticket ID
********************************************************************************

Not assigned.


Voting History
********************************************************************************

No vote yet.

