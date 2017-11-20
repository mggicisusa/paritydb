# Parity DB

Fast and reliable database, optimised for read operations.

[![Build Status][travis-image]][travis-url]

[travis-image]: https://travis-ci.org/paritytech/paritydb.svg?branch=master
[travis-url]: https://travis-ci.org/paritytech/paritydb

![db](./res/db.png)

### Database options

- journal eras (`usize`)
- preallocated memory (`u64`)
- extend threshold in % (`u8`)

### Database properties

- version (`u32`)
- used memory (`u64`)

### get operation

- check cache
- check journal
- read from memmap

### commit operation

- create and push new journal era

### flush operation

- create virtual commit from final journal eras
- delete journal eras
- copy content of virtual commit to memmap
- delete virtual commit

### rollback operation

- pop and delete journal era

### recover operation

- if valid virtual commit exists copy it to memmap and delete
- delete all invalid journal eras
