This document is about *how* to query using the Dataview plugin. If you want to learn what the Dataview plugin is used for, read the beginning of this documentation: [Dataview](https://blacksmithgu.github.io/obsidian-dataview/)
There are 3 ways to query:
1. DQL (Dataview Query Language)
2. Inline Query
3. JS Query

## DQL Query
A DQL Query consists of several parts:
- Exactly one [**Query Type**](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/) that determines what your Query Output looks like
- None or one [**FROM statement**](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands#from) to pick a specific tag or folder (or another [source](https://blacksmithgu.github.io/obsidian-dataview/reference/sources/)) to look at
- None to multiple [**other Data Commands**](https://blacksmithgu.github.io/obsidian-dataview/queries/data-commands/) that help you filter, group and sort your wanted output
A very simple example:
![[Pasted image 20241228125109.png]]
which lists all files in your vault.
A more restricted query may look like the following (example taken from the [documentation]([Dataview](https://blacksmithgu.github.io/obsidian-dataview/#data-querying)))
![[Pasted image 20241228125241.png]]
which lists all files in your vault that have the tag `#poems` and a [field](https://blacksmithgu.github.io/obsidian-dataview/annotation/add-metadata/) named `author` with the value `Edgar Allan Poe`. This query would find our example page from above.
- `LIST` is only one out of four [Query Types](https://blacksmithgu.github.io/obsidian-dataview/queries/query-types/) you can use. For example, with a `TABLE`, we could add some more information to our output: