# srdbi-plumbing

Scheme Relational Database Interface database plumbing

This is the basic interface to databases, per Peter Bex it's remit is roughly "how to set up a connection, how to send commands/prepare statements and how to navigate result sets".

## Remit:

- Hiding the concept of prepared statements

- Preventing statement injection in data; while this violates the plumbing focus, it should be enforced at the lowest level so every user of the srdbi set of SRFIs and libraries benefits from it.

- Standardization of errors, which would include its own ones like reporting the refusal to allow an injection attack.  Probably includes a disjoint type, so like the system errors in SRFI 170, would be its own SRFI to get around the library sharing issue.

- Ignoring the above injection prevention promise, an escape which allows executing arbitrary statements supplied as strings.  Not sure if or how this could or would include returning data other than success or failure.

## Undecided:

- Whether it handles transactions.

## What is does not do:

- Data types to the degree possible.

- SQL *per se* as a query and update language, most especially the differences between what the various databases support and how.
