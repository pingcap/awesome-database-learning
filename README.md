# Awesome Database Learning

A list of learning materials to understand databases internals, including but not limited to:

- papers
- blogs
- courses
- talks

Please submit a pull request if there is any material that you think should be included in this collection.

## Table of Contents

<!-- vim-markdown-toc GFM -->

* [Recommended Courses, Books and Talks](#recommended-courses-books-and-talks)
    * [Courses](#courses)
    * [Books](#books)
    * [Talks](#talks)
    * [Blogs](#blogs)
* [SQL & Relation Algebra](#sql--relation-algebra)
* [Query Optimizer](#query-optimizer)
    * [Planner Models](#planner-models)
    * [Subquery Optimization](#subquery-optimization)
    * [Join Order Optimization](#join-order-optimization)
    * [Functional Dependency & Physical Properties](#functional-dependency--physical-properties)
    * [Cost Model](#cost-model)
    * [Statistics](#statistics)
* [Query Execution](#query-execution)
    * [Execution Framework](#execution-framework)
    * [Vectorization vs Compilization](#vectorization-vs-compilization)
    * [Join](#join)
    * [Hash Table](#hash-table)
    * [Bloom Filter](#bloom-filter)
* [DDL](#ddl)
* [Relational Model](#relational-model)
    * [Codd's Rules](#codds-rules)
    * [Relational Data Model](#relational-data-model)
    * [Relational Algebra](#relational-algebra)
    * [ER to Relational Model](#er-to-relational-model)
    * [SQL - Overview](#sql---overview)
* [Transaction](#transaction)
    * [Isolation Levels](#isolation-levels)
    * [Concurrency Control](#concurrency-control)
* [Network](#network)
* [Storage](#storage)
    * [NoSQL Systems](#nosql-systems)
    * [Buffer Management](#buffer-management)
    * [Disk IO](#disk-io)
    * [B-Tree](#b-tree)
    * [LSM-Tree](#lsm-tree)
    * [Learned Indexes Structures](#learned-indexes-structures)
* [Serializing & RPC](#serializing--rpc)
* [Data Partitioning](#data-partitioning)
* [Replication & Consistency](#replication--consistency)
* [Consensus](#consensus)
* [Scheduling](#scheduling)
* [Benchmark & Testing](#benchmark--testing)
* [HTAP](#htap)
* [TLA+](#tla)

<!-- vim-markdown-toc -->

## Recommended Courses, Books and Talks

### Courses

- CMU [Database Systems (15-445/645)](https://15445.courses.cs.cmu.edu/fall2019/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
- CMU [Advanced Database Systems (15-721)](https://15721.courses.cs.cmu.edu/spring2020/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
- UC Berkeley [Introduction to Database Systems](https://cs186berkeley.net/calendar/)
- Stanford [Database System Implementation](https://web.stanford.edu/class/cs346/2015/)
- Cornell [Introduction to Database Systems](http://www.databaselecture.com/) by Prof. Trummer
- [Let's Build a Simple Database](https://cstack.github.io/db_tutorial/), thanks to [cstack](https://github.com/cstack)

### Books

- Stanford [Database Systems: The Complete Book](http://infolab.stanford.edu/~ullman/dscb.html)
- [Designing Data-Intensive Applications](http://shop.oreilly.com/product/0636920032175.do), [中文翻译](https://github.com/Vonng/ddia)
- [Database Internals](https://www.oreilly.com/library/view/database-internals/9781492040330/)
- [Foundations of Databases](http://webdam.inria.fr/Alice/)
- [Readings in Database Systems, 5th Edition](http://www.redbook.io/)
- [Database Design and Implementation: Second Edition (Data-Centric Systems and Applications)](https://www.amazon.com/dp/3030338355)
- [Principles of Distributed Database Systems, 4th ed](https://www.amazon.com/dp/3030262529)
- [Inside SQLite](https://books.google.com/books/about/Inside_SQLite.html?id=QoxUx8GOjKMC)
- [Architecture of a Database System](https://dsf.berkeley.edu/papers/fntdb07-architecture.pdf)
- [Relational Database Index Design and the Optimizers](https://www.amazon.com/Relational-Optimizers-Lahdenmaki-published-Wiley-Blackwell/dp/B00EKYLFSI)
- [Transactional Information Systems: Theory, Algorithms, and the Practice of Concurrency Control](https://www.sciencedirect.com/book/9781558605084/transactional-information-systems)

### Talks

- [Data Structures and Algorithms for Big Databases](https://people.csail.mit.edu/bradley/BenderKuszmaul-tutorial-xldb12.pdf)
- [A Journey From A Quick HackTo A High-Reliability Database Engine](https://www.sqlite.org/talks/wroclaw-20090310.pdf)

### Blogs

- [How does a relational database work](http://coding-geek.com/how-databases-work)
- [The Internals of PostgreSQL](http://www.interdb.jp/pg/index.html)
- [Books propose](https://cakebytheoceanluo.github.io/2020/03/10/books/)
- [what is database and its types](https://www.scaler.com/topics/dbms/what-is-database/)

## SQL & Relation Algebra

Courses:

- CMU [Database Systems (15-445/645)](https://15445.courses.cs.cmu.edu/fall2019/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
    - [Course Introduction and the Relational Model](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#aug-26-2019)
    - [Advanced SQL](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#aug-28-2019)

- UC Berkeley [Introduction to Database Systems](https://cs186berkeley.net/calendar/)
    - Introduction + SQL I
    - SQL II
    - Relational Algebra

## Query Optimizer

Courses:

- CMU [Database Systems (15-445/645)](https://15445.courses.cs.cmu.edu/fall2019/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
    - [Query Planning & Optimization I](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#oct-14-2019)
    - [Query Planning & Optimization II](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#oct-21-2019)

Blogs:

- [数据库内核杂谈](https://www.infoq.cn/theme/46), thanks to [顾仲贤](https://www.infoq.cn/profile/1780661/publish)
    - [数据库内核杂谈（七）：数据库优化器（上）](https://www.infoq.cn/article/GhhQlV10HWLFQjTTxRtA)
    - [数据库内核杂谈（八）：数据库优化器（下）](https://www.infoq.cn/article/JCJyMrGDQHl8osMFQ7ZR)
- [SQL优化器原理 - 查询优化器综述](https://yq.aliyun.com/articles/610128), thanks to [勿烦](https://yq.aliyun.com/users/kyni3qcv656rk?spm=a2c4e.11153940.0.0.6adc1a8etfb0vx)

### Planner Models

Blogs:

- [数据库内核杂谈](https://www.infoq.cn/theme/46), thanks to [顾仲贤](https://www.infoq.cn/profile/1780661/publish)
    - [数据库内核杂谈（九）：开源优化器 ORCA](https://www.infoq.cn/article/5o16eHOZ5zk6FzPSJpT2)
- [SQL 查询优化原理与 Volcano Optimizer 介绍](https://zhuanlan.zhihu.com/p/48735419), thanks to [张茄子](https://www.zhihu.com/people/chase-zh)
- [Cascades Optimizer](https://zhuanlan.zhihu.com/p/73545345), thanks to [hellocode](https://www.zhihu.com/people/hellocode-ming)

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

### Subquery Optimization

Blogs:

- [SQL 子查询的优化](https://zhuanlan.zhihu.com/p/60380557), thanks to [Eric Fu](https://www.zhihu.com/people/fuyufjh)
- [Calcite 子查询处理 - I (RemoveSubQuery)](https://zhuanlan.zhihu.com/p/62338250), thanks to [一只无情的小猫咪](https://www.zhihu.com/people/loop_recur)
- [Calcite 子查询处理 - II (Decorrelate)](https://zhuanlan.zhihu.com/p/66227661), thanks to [一只无情的小猫咪](https://www.zhihu.com/people/loop_recur)

Papers:

- 2001, [Orthogonal Optimization of Subqueries and Aggregation](http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.563.8492&rep=rep1&type=pdf), SIGMOD
- 2009, [Enhanced subquery optimizations in Oracle](https://www.researchgate.net/publication/220538535_Enhanced_Subquery_Optimizations_in_Oracle), VLDB
- 2015, [Unnesting Arbitrary Queries](http://www.btw-2015.de/res/proceedings/Hauptband/Wiss/Neumann-Unnesting_Arbitrary_Querie.pdf), BTW

### Join Order Optimization

Papers:

- 2006, [Analysis of Two Existing and One New Dynamic Programming Algorithm for the Generation of Optimal Bushy Join Trees without Cross Products](http://www.vldb.org/conf/2006/p930-moerkotte.pdf), VLDB
- 2015, [How Good Are Query Optimizers, Really?](http://www.vldb.org/pvldb/vol9/p204-leis.pdf), VLDB
- 2018, [Adaptive Optimization of Very Large Join Queries](https://db.in.tum.de/~radke/papers/hugejoins.pdf), SIGMOD

### Functional Dependency & Physical Properties

Thesis:

- 2000, [Exploiting Functional Dependence in Query Optimization](https://cs.uwaterloo.ca/research/tr/2000/11/CS-2000-11.thesis.pdf)

Papers:

- 1996, [Fundamental Techniques for Order Optimization](https://cs.uwaterloo.ca/~gweddell/cs798/p57-simmen.pdf), SIGMOD
- 2004, [An Efficient Framework for Order Optimization](https://www.researchgate.net/publication/4084912_An_efficient_framework_for_order_optimization), ICDE
- 2010, [Incorporating Partitioning and Parallel Plans into the SCOPE Optimizer](http://www.cs.albany.edu/~jhh/courses/readings/zhou10.pdf), ICDE

### Cost Model

Papers:

- 1996, [Modelling Costs for a MM-DBMS](), in Real-Time Databases
- 2014, [Approximation Schemes for Many-Objective Query Optimization](https://infoscience.epfl.ch/record/219202/files/p1299-trummer.pdf), SIGMOD
- 2015, [Multi-Objective Parametric Query Optimization](http://www.vldb.org/pvldb/vol8/p221-trummer.pdf), VLDB

### Statistics

Papers:

- 1984, [Accurate Estimation of the Number of Tuples Satisfying a Condition](https://dl.acm.org/doi/pdf/10.1145/971697.602294), SIGMOD
- 1993, [Optimal Histograms for Limiting Worst-Case Error Propagation in the Size of Join Results](https://dl.acm.org/doi/pdf/10.1145/169725.169708), ACM Trans. on Database Systems
- 1993, [Universality of Serial Histograms](https://pdfs.semanticscholar.org/deeb/d2fa377a41de49e5556ea948191a741faa1e.pdf), VLDB
- 1995, [Balancing Histogram Optimality and Practicality for Query Result Size Estimation](https://dl.acm.org/doi/pdf/10.1145/223784.223841), SIGMOD
- 1996, [Improved Histograms for Selectivity Estimation of Range Predicates](https://dl.acm.org/doi/pdf/10.1145/233269.233342), SIGMOD
- 1997, [SEEKing the truth about ad hoc join costs](https://dl.acm.org/doi/pdf/10.1007/s007780050043?download=true), VLDB
- 2000, [Towards Estimation Error Guarantees for Distinct Values](https://dl.acm.org/doi/pdf/10.1145/335168.335230), SIGMOD/PODS
- 2001, [Distinct Sampling for Highly-Accurate Answers to Distinct Values Queries and Event Reports](http://vldb.org/conf/2001/P541.pdf), VLDB
- 2003, [The History of Histograms](http://www.vldb.org/conf/2003/papers/S02P01.pdf), VLDB
- 2005, [An Improved Data Stream Summary: The Count-Min Sketch and its Applications](http://dimacs.rutgers.edu/~graham/pubs/papers/cm-full.pdf), Journal of Algorithms
- 2007, [New Estimation Algorithms for Streaming Data: Count-min Can Do More](http://webdocs.cs.ualberta.ca/~drafiei/papers/cmm.pdf)
- 2009, [Preventing Bad Plans by Bounding the Impact of Cardinality Estimation Errors](https://dl.acm.org/doi/pdf/10.14778/1687627.1687738), VLDB
- 2010, [Histograms Reloaded: The Merits of Bucket Diversity](https://dl.acm.org/doi/pdf/10.1145/1807167.1807239), SIGMOD
- 2014, [Exploiting Ordered Dictionaries to Efficiently Construct Histograms with Q-Error Guarantees in SAP HANA](https://dl.acm.org/doi/pdf/10.1145/2588555.2595629), SIGMOD
- 2017, [Adaptive Statistics in Oracle 12c](http://www.vldb.org/pvldb/vol10/p1813-zait.pdf), VLDB
- 2019, [Pessimistic Cardinality Estimation: Tighter Upper Bounds for Intermediate Join Cardinalities](https://dl.acm.org/doi/pdf/10.1145/3299869.3319894), SIGMOD
- 2019, [Deep Unsupervised Cardinality Estimation](http://www.vldb.org/pvldb/vol13/p279-yang.pdf), VLDB
- 2020, [NeuroCard: One Cardinality Estimator for All Tables](https://vldb.org/pvldb/vol14/p61-yang.pdf), VLDB

Books:
- [Synopses for Massive Data: Samples, Histograms, Wavelets, Sketches](https://db.cs.berkeley.edu/cs286/papers/synopses-fntdb2012.pdf)

## Query Execution

Courses:

- CMU [Database Systems (15-445/645)](https://15445.courses.cs.cmu.edu/fall2019/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
    - [Query Execution I](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#oct-07-2019)
    - [Query Execution II](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#oct-09-2019)

### Execution Framework

Papers:

- 1994, [Volcano-An Extensible and Parallel Query Evaluation System](https://paperhub.s3.amazonaws.com/dace52a42c07f7f8348b08dc2b186061.pdf), IEEE Transactions on Knowledge and Data EngineeringFebruary
- 2014, [Morsel-Driven Parallelism: A NUMA-Aware Query Evaluation Framework for the Many-Core Age](https://15721.courses.cs.cmu.edu/spring2019/papers/14-scheduling/p743-leis.pdf), SIGMOD

### Vectorization vs Compilization

Blogs:

- [Overhead of a Generalized Query Execution Engine](https://github.com/pivotal/blog/blob/master/content/post/codegen-gpdb-qx.md), from [The Pivotal Engineering Journal](https://github.com/pivotal/blog), thanks to the Pivotal Engineering team

Papers:

- 2005, [MonetDB/X100: Hyper-Pipelining Query Execution](http://cidrdb.org/cidr2005/papers/P19.pdf), CIDR
- 2011, [Efficiently Compiling Efficient Query Plans for Modern Hardware](https://www.vldb.org/pvldb/vol4/p539-neumann.pdf), VLDB
- 2017, [Relaxed Operator Fusion for In-Memory Databases: Making Compilation, Vectorization, and Prefetching Work Together At Last](http://www.vldb.org/pvldb/vol11/p1-menon.pdf), VLDB
- 2018, [Everything You Always Wanted to Know About Compiled and Vectorized Queries But Were Afraid to Ask](http://www.vldb.org/pvldb/vol11/p2209-kersten.pdf), VLDB
- 2018, [Adaptive Execution of Compiled Queries](https://db.in.tum.de/~leis/papers/adaptiveexecution.pdf), ICDE

### Join

Papers:

- 2013, [Multi-Core, Main-Memory Joins: Sort vs. Hash Revisited](http://www.vldb.org/pvldb/vol7/p85-balkesen.pdf), VLDB
- 2017, [Looking Ahead Makes Query Plans Robust](http://www.vldb.org/pvldb/vol10/p889-zhu.pdf), VLDB

### Hash Table

Courses:

- CMU [Database Systems (15-445/645)](https://15445.courses.cs.cmu.edu/fall2019/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
    - [Hash Tables](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#sep-16-2019)

Blogs:

- [Fibonacci Hashing: The Optimization that the World Forgot (or: a Better Alternative to Integer Modulo)](https://probablydance.com/2018/06/16/fibonacci-hashing-the-optimization-that-the-world-forgot-or-a-better-alternative-to-integer-modulo/), thanks to [Malte Skarupke](https://probablydance.com/)
- [All hash table sizes you will ever need](https://databasearchitects.blogspot.com/2020/01/all-hash-table-sizes-you-will-ever-need.html), thanks to [Database Architects - Thomas Neumann](https://databasearchitects.blogspot.com/)

### Bloom Filter

Papers:
- 2018, [SuRF: Practical Range Query Filtering with Fast Succinct Tries](https://www.cs.cmu.edu/~pavlo/papers/mod601-zhangA-hm.pdf), SIGMOD


## DDL

- 2013, [Online, Asynchronous Schema Change in F1](https://research.google.com/pubs/archive/41376.pdf), VLDB

## Relational Model

Blogs: 

- [What is a Relational Database?](https://www.calebcurry.com/what-is-a-relational-database/), thanks to [Caleb Curry](https://www.calebcurry.com/author/calebcurry_rlrc3d/)
- [What is a Relational Database?](https://careerkarma.com/blog/relational-database/),thank to [JAMES GALLAGHER](https://careerkarma.com/blog/author/jamesgallagher/)

### Codd's Rules

Blogs:

- [Codd’s Rules for Relational Database Systems](https://www.oreilly.com/library/view/sql-in-a/9780596155322/ch01s01s01.html), thanks to [Kevin Kline](https://en.wikipedia.org/wiki/Kevin_Kline)

### Relational Data Model

Blogs:

- [Relational model](https://en.wikipedia.org/wiki/Relational_model), thanks to [Wikipedia](https://en.wikipedia.org/wiki/Wikipedia)

### Relational Algebra

Blogs:

- [Introduction of Relational Algebra in DBMS](https://www.geeksforgeeks.org/introduction-of-relational-algebra-in-dbms/#:~:text=Relational%20Algebra%20is%20procedural%20query,column%20data%20from%20a%20relation.), thanks to [GeeksforGeeks](https://www.linkedin.com/company/geeksforgeeks?originalSubdomain=in)

### ER to Relational Model

Blogs:

- [ER Model to Relational Model](https://www.tutorialspoint.com/dbms/er_model_to_relational_model.htm), thanks to [tutorialspoint](https://www.tutorialspoint.com/index.htm1)

### SQL - Overview

Tutorials: 

- [Interactive SQL tutorials and a sandbox to learn SQL step by step](https://interactivesql.com)

Blogs:

- [An Overview of SQL Text Functions](https://learnsql.com/blog/), thanks to [Zahin Rahman](https://learnsql.com/authors/zahin-rahman/)

## Transaction

### Isolation Levels

Blogs:

- [一致性模型](https://www.jianshu.com/p/3673e612cce2), thanks to [siddontang](https://www.jianshu.com/u/1yJ3ge)

Papers:

- 1995, [A Critique of ANSI SQL Isolation Levels](https://www.microsoft.com/en-us/research/wp-content/uploads/2016/02/tr-95-51.pdf), SIGMOD
- 2000, [Generalized Isolation Level Definitions](http://pmg.csail.mit.edu/papers/icde00.pdf), Proceedings of 16th International Conference on Data Engineering

### Concurrency Control

Courses:

- CMU [Database Systems (15-445/645)](https://15445.courses.cs.cmu.edu/fall2019/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
    - [Concurrency Control Theory](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#oct-23-2019)
    - [Two-Phase Locking Concurrency Control](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#oct-28-2019)
    - [Timestamp Ordering Concurrency Control](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#oct-30-2019)
    - [Multi-Version Concurrency Control](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#nov-04-2019)

- CMU [Advanced Database Systems (15-721)](https://15721.courses.cs.cmu.edu/spring2020/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
    - [Multi-Version Concurrency Control (Design Decisions)](https://15721.courses.cs.cmu.edu/spring2020/schedule.html#jan-22-2020)
    - [Multi-Version Concurrency Control (Protocols)](https://15721.courses.cs.cmu.edu/spring2020/schedule.html#jan-27-2020)
    - [Multi-Version Concurrency Control (Garbage Collection)](https://15721.courses.cs.cmu.edu/spring2020/schedule.html#jan-29-2020)

Papers:

- 1976, [The Notions of Consistency and Predicate Locks in a Database System](http://jimgray.azurewebsites.net/papers/on%20the%20notions%20of%20consistency%20and%20predicate%20locks%20in%20a%20database%20system%20cacm.pdf), Communications of the ACM
- 1981, [Concurrency Control in Distributed Database Systems](https://people.eecs.berkeley.edu/~brewer/cs262/concurrency-distributed-databases.pdf), ACM Computing Surveys
- 1981, [On Optimistic Methods for Concurrency Control](https://www.eecs.harvard.edu/~htk/publication/1981-tods-kung-robinson.pdf), ACM Transactions on Database Systems
- 1983, [Multiversion Concurrency Control - Theory and Algorithms](https://sites.fas.harvard.edu/~cs265/papers/bernstein-1983.pdf), ACM Transactions on Database Systems
- 2012, [Serializable Snapshot Isolation in PostgreSQL](http://www.vldb.org/pvldb/vol4/p783-jung.pdf), VLDB
- 2012, [Calvin: Fast Distributed Transactions for Partitioned Database Systems](http://cs.yale.edu/homes/thomson/publications/calvin-sigmod12.pdf), SIGMOD
- 2014, [MaaT: effective and scalable coordination of distributed transactions in the cloud](http://www.nawab.me/Uploads/MaaT_VLDB2014.pdf), VLDB
- 2014, [Staring into the Abyss: An Evaluation of Concurrency Control with One Thousand Cores](http://www.vldb.org/pvldb/vol8/p209-yu.pdf), VLDB
- 2014, [An Evaluation of the Advantages and Disadvantages of Deterministic Database Systems](http://www.vldb.org/pvldb/vol7/p821-ren.pdf), VLDB
- 2015, [Fast Serializable Multi-Version Concurrency Control for Main-Memory Database Systems](https://db.in.tum.de/~muehlbau/papers/mvcc.pdf), SIGMOD
- 2017, [An Empirical Evaluation of In-Memory Multi-Version Concurrency Control](http://www.vldb.org/pvldb/vol10/p781-Wu.pdf), VLDB
- 2017, [An Evaluation of Distributed Concurrency Control](https://www.vldb.org/pvldb/vol10/p553-harding.pdf), VLDB
- 2019, [Scalable Garbage Collection for In-Memory MVCC Systems](https://db.in.tum.de/~boettcher/p128-boettcher.pdf), VLDB

## Network

Courses:

- CMU [Advanced Database Systems (15-721)](https://15721.courses.cs.cmu.edu/spring2020/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
    - [Networking Protocols](https://15721.courses.cs.cmu.edu/spring2020/schedule.html#feb-19-2020)

Papers:

- 2016, [The End of Slow Networks: It's Time for a Redesign](http://www.vldb.org/pvldb/vol9/p528-binnig.pdf), VLDB
- 2016, [Accelerating Relational Databases by Leveraging Remote Memory and RDMA](https://15721.courses.cs.cmu.edu/spring2020/papers/11-networking/li-sigmod2016.pdf), SIGMOD
- 2017, [Don't Hold My Data Hostage: A Case for Client Protocol Redesign](http://www.vldb.org/pvldb/vol10/p1022-muehleisen.pdf), VLDB

## Storage

### NoSQL Systems

Papers:

- 2006, [Bigtable: A Distributed Storage System for Structured Data](https://static.googleusercontent.com/media/research.google.com/en//archive/bigtable-osdi06.pdf), OSDI
- 2007, [Dynamo: Amazon’s Highly Available Key-value Store](https://sites.cs.ucsb.edu/~agrawal/fall2009/dynamo.pdf), SOSP
- 2008, [PNUTS: Yahoo!’s Hosted Data Serving Platform](https://sites.cs.ucsb.edu/~agrawal/fall2009/PNUTS.pdf), VLDB
- 2010, [Cassandra - A Decentralized Structured Storage System](https://www.cs.cornell.edu/projects/ladis2009/papers/lakshman-ladis2009.pdf), SOSP
- 2019, [PNUTS to Sherpa: Lessons from Yahoo!’s Cloud Database ](http://www.vldb.org/pvldb/vol12/p2300-cooper.pdf), VLDB

### Buffer Management

Courses:

- CMU [Database Systems (15-445/645)](https://15445.courses.cs.cmu.edu/fall2019/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
    - [Buffer Pools](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#sep-11-2019)

Papers:

- 1987, [The 5 Minute Rule for Trading Memory for Disc Accesses and the 5 Byte Rule for Trading Memory for CPU Time](https://www.hpl.hp.com/techreports/tandem/TR-86.1.pdf), SIGMOD
- 2008, [The Five Minute Rule 20 Years Later and How Flash Memory Changes the Rules](https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.227.3846&rep=rep1&type=pdf), ACM Queue
- 2018, [Managing Non-Volatile Memory in Database Systems](https://db.in.tum.de/people/sites/vanrenen/papers/HyMem.pdf?lang=de), SIGMOD
- 2018, [LeanStore: In-Memory Data Management Beyond Main Memory](https://db.in.tum.de/~leis/papers/leanstore.pdf), ICDE
- 2020, [Umbra: A Disk-Based System with In-Memory Performance](http://cidrdb.org/cidr2020/papers/p29-neumann-cidr20.pdf), CIDR

### Disk IO

Blogs:

- [On Disk IO, Part 1: Flavors of IO](https://medium.com/databasss/on-disk-io-part-1-flavours-of-io-8e1ace1de017), thanks to [Alex](https://twitter.com/ifesdjeen)
- [On Disk IO, Part 2: More Flavours of IO](https://medium.com/databasss/on-disk-io-part-2-more-flavours-of-io-c945db3edb13?), thanks to [Alex](https://twitter.com/ifesdjeen)
- [On Disk IO, Part 3: LSM Trees](https://medium.com/databasss/on-disk-io-part-3-lsm-trees-8b2da218496f), thanks to [Alex](https://twitter.com/ifesdjeen)
- [On Disk IO, Part 4: B-Trees and RUM Conjecture](https://medium.com/databasss/on-disk-storage-part-4-b-trees-30791060741), thanks to [Alex](https://twitter.com/ifesdjeen)
- [On Disk IO, Part 5: Access Patterns in LSM Trees](https://medium.com/databasss/on-disk-io-access-patterns-in-lsm-trees-2ba8dffc05f9), thanks to [Alex](https://twitter.com/ifesdjeen)
- [Ensuring data reaches disk(LWN)](https://lwn.net/Articles/457667/)
- [Read, write & space amplification - pick 2](http://smalldatum.blogspot.com/2015/11/read-write-space-amplification-pick-2_23.html), thanks to [Mark Callaghan](https://twitter.com/markcallaghandb)

Papers:

- 2016, [Design Tradeoffs of Data Access Methods](http://scholar.harvard.edu/files/stratos/files/rum-tutorial.pdf?m=1461167186), SIGMOD
- 2016, [Designing Access Methods: The RUM Conjecture](https://stratos.seas.harvard.edu/files/stratos/files/rum.pdf), EDBT

### B-Tree

Blogs:

- [B树、B+树索引算法原理（上）](https://www.codedump.info/post/20200609-btree-1/) thanks to [codedump](https://www.codedump.info/)
- [B树、B+树索引算法原理（下）](https://www.codedump.info/post/20200615-btree-2/)

Courses:

- CMU [Database Systems (15-445/645)](https://15445.courses.cs.cmu.edu/fall2019/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
    - [Trees Indexes I](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#sep-18-2019)
    - [Trees Indexes II](https://15445.courses.cs.cmu.edu/fall2019/schedule.html#sep-23-2019)

- CMU [Advanced Database Systems (15-721)](https://15721.courses.cs.cmu.edu/spring2020/schedule.html), thanks to [Andy Pavlo](http://www.cs.cmu.edu/~pavlo/)
    - [OLTP Indexes (B+Tree Data Structures)](https://15721.courses.cs.cmu.edu/spring2020/schedule.html#feb-03-2020)

Papers:

- 1979, [The Ubiquitous B-Tree](http://carlosproal.com/ir/papers/p121-comer.pdf)

### LSM-Tree

Papers:

- 1996, [The Log-Structured Merge-Tree (LSM-Tree)](https://www.cs.umb.edu/~poneil/lsmtree.pdf),
- 2014, [A Comparison of Fractal Trees to Log-Structured Merge (LSM) Trees](http://www.pandademo.com/wp-content/uploads/2017/12/A-Comparison-of-Fractal-Trees-to-Log-Structured-Merge-LSM-Trees.pdf)
- 2017, [WiscKey: Separating Keys from Values in SSD-conscious Storage](https://www.usenix.org/system/files/conference/fast16/fast16-papers-lu.pdf), TOS
- 2019, [LSM-based Storage Techniques: A Survey](https://arxiv.org/pdf/1812.07527.pdf)

### Learned Indexes Structures

Papers:

- 2018, [The Case for Learned Index Structures](https://www.cl.cam.ac.uk/~ey204/teaching/ACS/R244_2018_2019/papers/Kraska_SIGMOD_2018.pdf)
- 2019, [Learning Multi-dimensional Indexes](https://arxiv.org/pdf/1912.01668.pdf)
- 2020, [XIndex: A Scalable Learned Index for Multicore Data Storage](https://dl.acm.org/doi/pdf/10.1145/3332466.3374547)
- 2020, [RadixSpline: A Single-Pass Learned Index](https://dl.acm.org/doi/10.1145/3401071.3401659), [Source Code](https://github.com/learnedsystems/RadixSpline), aiDM@SIGMOD
- 2020, [The PGM-index: a fully-dynamic compressed learned index with provable worst-case bounds](http://www.vldb.org/pvldb/vol13/p1162-ferragina.pdf), [Source Code](https://github.com/gvinciguerra/PGM-index), VLDB
- 2020, [From WiscKey to Bourbon: A Learned Index for Log-Structured Merge Trees](http://pages.cs.wisc.edu/~yifann/bourbon-osdi20.pdf)

## Serializing & RPC

- [Protocol Buffers Developer Guide](https://developers.google.com/protocol-buffers/docs/overview)
- [gRPC Documntation](https://www.grpc.io/docs/quickstart/go/)

## Data Partitioning

Blogs:

- [TiDB Internal (I) - Data Storage](https://pingcap.com/blog/2017-07-11-tidbinternal1/)
- [Partitioning Behavior of DynamoDB](https://dzone.com/articles/partitioning-behavior-of-dynamodb), thanks to [Parth Modi](https://dzone.com/users/3098371/parthmodi.html)

Papers:

- 2007, [Dynamo: Amazon’s Highly Available Key-value Store](https://www.allthingsdistributed.com/files/amazon-dynamo-sosp2007.pdf), SOSP

## Replication & Consistency

Blogs:

- [Tick or Tock? Keeping Time and Order in Distributed Databases](https://dzone.com/articles/tick-or-tock-keeping-time-and-order-in-distributed-1), thanks to [Liu Tang](https://dzone.com/users/3186309/siddontang.html)

Papers:

- 2012, [Consistency Tradeoffs in Modern Distributed Database System Design](http://www.cs.umd.edu/~abadi/papers/abadi-pacelc.pdf)
- 2020, [Strong and Efficient Consistency with Consistency-Aware Durability ](http://pages.cs.wisc.edu/~ag/cad.pdf), FAST 2020

## Consensus

Technical report:

- University of Cambridge [Distributed consensus revised](https://www.cl.cam.ac.uk/techreports/UCAM-CL-TR-935.pdf), a great paper about Consenssus especially Paxos and Paxos-Related algorithms, by Heidi Howard

Papers:

- 2014, [Ark: A Real-World Consensus Implementation](https://arxiv.org/pdf/1407.4765.pdf), CoRR

## Scheduling

Blogs:

- [Building a Large-scale Distributed Storage System Based on Raft](https://www.cncf.io/blog/2019/11/04/building-a-large-scale-distributed-storage-system-based-on-raft/), by Ed Huang

Papers:

- 2016, [Automated Demand-driven Resource Scaling in Relational Database-as-a-Service](http://www.audentia-gestion.fr/MICROSOFT/p883-das.pdf), SIGMOD
- 2019, [Autoscaling Tiered Cloud Storage in Anna](https://dl.acm.org/doi/pdf/10.14778/3311880.3311881), VLDB
- 2020, [Adaptive HTAP through Elastic Resource Scheduling](https://dl.acm.org/doi/pdf/10.1145/3318464.3389783), SIGMOD
- 2020, [MorphoSys: Automatic Physical Design Metamorphosis for Distributed Database Systems](http://www.vldb.org/pvldb/vol13/p3573-abebe.pdf), VLDB

## Benchmark & Testing

Blogs:

- [Use go-ycsb to benchmark different databases (1)](https://medium.com/@siddontang/use-go-ycsb-to-benchmark-different-databases-8850f6edb3a7), thanks to [siddontang](https://medium.com/@siddontang)
- [Chaos Tools and Techniques for Testing the TiDB Distributed NewSQL Database](https://dzone.com/articles/chaos-tools-and-techniques-for-testing-the-tidb-di-1), thanks to [Liu Tang](https://dzone.com/users/3186309/siddontang.html)
- [Creating Custom Sysbench Scripts](https://www.percona.com/blog/2019/04/25/creating-custom-sysbench-scripts/), thanks to [Matthew Boehm](https://www.percona.com/blog/author/matthew-boehm/)


Papers:

- 2010, [Benchmarking Cloud Serving Systems with YCSB](https://courses.cs.duke.edu/fall13/compsci590.4/838-CloudPapers/ycsb.pdf), SOCC

## HTAP

Papers:

- 2020, [TiDB: A Raft-based HTAP Database](http://www.vldb.org/pvldb/vol13/p3072-huang.pdf), VLDB
- 2020, [F1 Lightning: HTAP as a Service](http://www.vldb.org/pvldb/vol13/p3313-yang.pdf), VLDB

## TLA+

Talks:
- [The TLA+ Video Course](http://lamport.azurewebsites.net/video/videos.html)
