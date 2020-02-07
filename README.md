# Awesome Database Learning

A list of learning materials to understand databases internals, including but not limited to:

- papers
- blogs
- courses
- talks

Please submit a pull request if there is any material that you think should be included in this collection.

## Table of Contents

<!-- vim-markdown-toc GFM -->

* [SQL & Relation Algebra](#sql--relation-algebra)
* [Query Optimizer](#query-optimizer)
    * [Planner Models](#planner-models)
    * [Cost Model](#cost-model)
    * [Statistics](#statistics)
* [Query Execution](#query-execution)
* [DDL](#ddl)
* [Transaction](#transaction)
* [Network](#network)
* [Storage](#storage)
    * [Disk IO](#disk-io)
    * [B-Tree](#b-tree)
    * [LSM-Tree](#lsm-tree)
* [Serializing & RPC](#serializing--rpc)
* [Data Partitiioning](#data-partitiioning)
* [Replication & Consistency](#replication--consistency)
* [Consensus](#consensus)
* [Scale & Blance](#scale--blance)
* [Benchmark & Testing](#benchmark--testing)

<!-- vim-markdown-toc -->

## SQL & Relation Algebra

Courses:

- CMU [Database Systems (15-445/645)](https://15445.courses.cs.cmu.edu/fall2019/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
    - Course Introduction and the Relational Model.
    - Advanced SQL.

- UC Berkeley [Introduction to Database Systems](https://cs186berkeley.net/calendar/)
    - Introduction + SQL I
    - SQL II
    - Relational Algebra

## Query Optimizer

Blogs:

- [数据库内核杂谈](https://www.infoq.cn/theme/46), thanks to [顾仲贤](https://www.infoq.cn/profile/1780661/publish)
    - [数据库内核杂谈（七）：数据库优化器（上）](https://www.infoq.cn/article/GhhQlV10HWLFQjTTxRtA)
    - [数据库内核杂谈（八）：数据库优化器（下）](https://www.infoq.cn/article/JCJyMrGDQHl8osMFQ7ZR)

### Planner Models

Papers:

- 1979, [Access Path Selection in a Relational Database Management System](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.71.3735&rep=rep1&type=pdf), SIGMOD
- 1979, [Query Processing in Main Memory Database Management Systems](http://15721.courses.cs.cmu.edu/spring2016/papers/p239-lehman.pdf), VLDB
- 1987, [Query Optimization by Simulated Annealing](http://ftp.cs.wisc.edu/pub/techreports/1987/TR693.pdf), SIGMOD
- 1988, [Grammar-like Functional Rules for Representing Query Optimization Alternatives](https://people.eecs.berkeley.edu/~brewer/cs262/23-lohman88.pdf), SIGMOD
- 1993, [The Volcano Optimizer Generator- Extensibility and Efficient Search](https://pdfs.semanticscholar.org/a817/a3e74d1663d9eb35b4baf3161ab16f57df85.pdf), ICDE
- 1995, [The Cascades Framework for Query Optimization](https://pdfs.semanticscholar.org/360e/cdfc79850873162ee4185bed8f334da30031.pdf), IEEE Data engineering Bulltin
- 1998, [An Overview of Query Optimization in Relational Systems](https://web.stanford.edu/class/cs345d-01/rl/chaudhuri98.pdf), PODS
- 2001, [LEO – DB2’s LEarning Optimizer](http://15721.courses.cs.cmu.edu/spring2016/papers/stillger-vldb2001.pdf), VLDB
- 2004, [Robust Query Processing through Progressive Optimization](https://www.cse.iitb.ac.in/infolab/Data/Courses/CS632/2006/Papers/sigmod04-markl.pdf), SIGMOD
- 2014, [Orca: A Modular Query Optimizer Architecture for Big Data](http://15721.courses.cs.cmu.edu/spring2016/papers/p337-soliman.pdf), SIGMOD
- 2016, [Parallelizing Query Optimization on Shared-Nothing Architectures](http://www.vldb.org/pvldb/vol9/p660-trummer.pdf), VLDB
- 2016, [The MemSQL Query Optimizer: A modern optimizer for real-time analytics in a distributed database](http://www.vldb.org/pvldb/vol9/p1401-chen.pdf), VLDB

Blogs:

- [数据库内核杂谈](https://www.infoq.cn/theme/46), thanks to [顾仲贤](https://www.infoq.cn/profile/1780661/publish)
    - [数据库内核杂谈（九）：开源优化器 ORCA](https://www.infoq.cn/article/5o16eHOZ5zk6FzPSJpT2)

### Cost Model

Papers:

- 1996, [Modelling Costs for a MM-DBMS](), in Real-Time Databases
- 2014, [Approximation Schemes for Many-Objective Query Optimization](https://infoscience.epfl.ch/record/219202/files/p1299-trummer.pdf), SIGMOD
- 2015, [Multi-Objective Parametric Query Optimization](http://www.vldb.org/pvldb/vol8/p221-trummer.pdf), VLDB

### Statistics

Papers:

- 2005, [An Improved Data Stream Summary: The Count-Min Sketch and its Applications](http://dimacs.rutgers.edu/~graham/pubs/papers/cm-full.pdf), Journal of Algorithms
- 2007, [New Estimation Algorithms for Streaming Data: Count-min Can Do More](http://webdocs.cs.ualberta.ca/~drafiei/papers/cmm.pdf)
- 2017, [Adaptive Statistics in Oracle 12c](http://www.vldb.org/pvldb/vol10/p1813-zait.pdf), VLDB

Books:
- [Synopses for Massive Data: Samples, Histograms, Wavelets, Sketches](https://db.cs.berkeley.edu/cs286/papers/synopses-fntdb2012.pdf)


## Query Execution

## DDL

## Transaction

## Network

## Storage

### Disk IO

### B-Tree

### LSM-Tree

## Serializing & RPC

## Data Partitiioning

## Replication & Consistency

## Consensus

## Scale & Blance

## Benchmark & Testing
