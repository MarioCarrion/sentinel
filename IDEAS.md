# Sentinel Ideas

This file is basically an _ideas dumpster_, where good and bad ideas live together in harmony.

## Expirable Resources

The concept of _Expirable Resource_ can be represented easily as a **Plugin**. Some questions to answer:

1. Should I use Go routines for processing all configured plugins?
2. Should I not use Go routines and instead process all plugins sequentially?
3. Should I use a job scheduler to periodically run all of them?

## Losing connection to the Server

1. What's the in-memory buffer size when losing connection to Server?
2. When to start dumping to disk? After how many retries? Should it be configurable?
