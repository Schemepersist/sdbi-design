# sdbi-design

Scheme Database Interface (sdbi) design notes etc.

This is the basic Scheme interface to databases, [per Peter
Bex](https://srfi-email.schemers.org/schemepersist/msg/12145753/) its
top level user API is roughly "how to set up a connection, how to send
commands/prepare statements, and how to navigate result sets".

## Remit:

- Can supporting all databases with a text query language that return
  rectangular results.

- Hiding the concept of preparing statements

- Preventing statement injection in data; while this violates the
  plumbing focus, it should be enforced at the lowest level so every
  user of the sdbi set of SRFIs and libraries benefits from it.

- Standardization of errors, which would include its own ones like
  reporting the refusal to allow an injection attack.  Probably will
  be combined with the system errors in SRFI 170, and provide a
  disjoint type, so will be its own SRFI to get around the library
  sharing issue.

- Ignoring the above injection prevention promise, an escape which
  allows executing arbitrary statements supplied as strings.  Not sure
  if or how this could or would include returning data other than
  success or failure.

## Undecided:


## What is does not do:

