---
title: I just learned SQL!
category: "code"
cover: servers.jpg
author: getter hiss
---

# I just learned SQL!

So I just learned some SQL. It's been pretty neat.

When I first started programming, I learned MongoDB. That seems to be the default most Javascript programmers first learn since it's a familiar syntax with the Dot Notation (i.e. `db.users.get()`).

The problem with [MongoDB](https://www.mongodb.com/), or downside, is that it is a NoSQL database. The data is not related at all in each collection. Of course MongoDB has it's [Aggregation framework](https://university.mongodb.com/courses/M121/about) and now as of Version 4.0, it added [ACID transactions](https://www.mongodb.com/mongodb-4.0), it was just never meant to be a relational database.

## Relational Database

![CockroachDB](./crdb.png "CockroachDB") I just learned what this is and the power of it. Writing SQL is definitely different, but I am seeing it's power.

I am doing my new What3.xyz API with a [PostgreSQL](https://www.postgresql.org/) database, more specifically, [CockroachDB](https://www.cockroachlabs.com/) which is based on the PostgreSQL protocol. 

## CockroachDB

Yeah, we all know about the name. Everyone talks about it when they first here it. But let me tell you, the idea of having your [database act like a CDN](https://www.cockroachlabs.com/blog/distributed-database-performance/) is truly compelling.

## Notes

Here are some of my notes for people to get started. You can also check out my [github commit](https://github.com/what3xyz/api/blob/f56fa6979b44e42812d9f2d89cba578e2234c6f8/package.json) with these commands in action.

Once you have [cockroachDB installed](https://www.cockroachlabs.com/docs/stable/install-cockroachdb.html), you can run commands from the built in SQL client: 

`cockroach sql --insecure`

You can run the following commands:

```sql
SHOW DATABASES;
CREATE DATABASE what3xyz;
USE what3xyz;
SHOW TABLES;
SHOW COLUMNS FROM ideas;
SELECT * FROM ideas;
SELECT id, idea, tags, uid, created, modified FROM ideas;
SELECT * FROM ideas WHERE active=true ORDER BY created DESC LIMIT 1 OFFSET 1;
```