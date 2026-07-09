VBASE:

Relaxed monotonicity (early stopping)

https://www.usenix.org/system/files/osdi23-zhang-qianxi_1.pdf

JVector has a simple implementation: TODO link: RelaxedMonotonicityTracker


Indexing Centroids?

CSPG: Crossing Sparse Proximity Graphs for Approximate Nearest Neighbor Search

https://neurips.cc/virtual/2024/poster/93606

Fast clustering:

Note: Also interesting block scoring mechanism

https://github.com/cwida/SuperKMeans


Overspilling Idea:
 - Forward linking overspilling. Instead of simply adding a document vector to its next set of nearest centroids, you determine the true nearest K vectors for document vector X document vector and pull them into X's nearest centroid. This will require deduplication for when X's same clustered vectors get overlapping, and of course, some sane upper limits on size. This will adjust the "fuzzy overpilling" issue where just the next centroid is considered. Though I suspect it will increase indexing time.