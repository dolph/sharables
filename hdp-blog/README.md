# Announcing our first Hortonworks Data Platform (HDP) and Watson Studio Local code pattern

> First a quick note - until just recently, Watson Studio Local was named Data Science Experience (DSX) Local. Please note this as some of the links below may still refer to the product using the old name.

Following an announcement that designated [Watson Studio Local as certified to work with HDP](https://hortonworks.com/blog/certification-ibm-data-science-experience-dsx-hdp-win-win-customers), our team decided to create a set of code patterns. The code patterns would need to showcase how a user could leverage the two offerings to simplify and accelerate their AI development goals.

We're happy to announce that we've completed our first code pattern, aptly entitled, [INSERT TITLE OF CODE PATTERN HERE](https://developer.ibm.com/code/patterns/sms-spam-filter-using-hortonworks/)! The focus of this first code pattern was to provide an easy-to-follow set of examples that showcase how a user might integrate the two platforms.

In this blog post we will:

* Describe what the new code pattern does,
* Provide a brief overview of HDP and Watson Studio Local, and
* Explain how the two platforms interact to accomplish the goals of the code pattern.

Many thanks to [Zohar Nissare-Houssen](https://www.linkedin.com/in/all-about-zohar/), [Ali Bajwa](https://www.linkedin.com/in/aliabajwa/) and [Nadeem Asghar](https://www.linkedin.com/in/nadeem-asghar/) for their guidance on all technical matters related to HDP as we developed the code pattern.

## What's a Spam Filter?

A Spam filter is a type of classification model that can determine if any given SMS text message is spam, or ham (a legitimate message). In our code pattern, we attempt to build such a filter. 

We start by examining and processing real-life trained data. In our case, we used a publicly available [dataset](https://www.kaggle.com/ishansoni/sms-spam-collection-dataset) from [kaggle.com](https://www.kaggle.com). The dataset contains over 5K messages, each tagged appropriately as spam or ham. Using natural language processing and machine learning algorithms, we take you through the process of building and training our Spam Filter classification model.

## A brief intro to Watson Studio Local and HDP

As mentioned in the title, this code pattern made use of Watson Studio Local and HDP. We'll briefly describe both in this section before diving into how we used the two together.

### What is Watson Studio Local?

[IBM Watson Studio Local](https://content-dsxlocal.mybluemix.net/docs/content/local/overview.html) is an out-of-the-box on premises solution for data scientists and data engineers. It addresses the entire Data Science life cycle and provides an environment where data scientists can work with a variety of tools such as Spark, R, Python and Anaconda - all integrated to work together in a productive collaborative experience. Either due to GDPR or other data privacy related issues, **Watson Studio Local is perfect for users wanting to perform complex data science related work in the security of their private network**.

Aside from running notebooks, Watson Studio also provides projects for multi-tenancy and collaboration, identity hooks for LDAP, an admin console for management, a community tab for finding sample content, integration with GitHub and GitHub Enterprise, oh, and it's deployable to IBM's popular [IBM Cloud Private](https://www.ibm.com/analytics/cloud-private-for-data). Below is a architectural overview of Watson Studio Local.

![](images/dsx-local-arch.png)

### What is HortonWorks Data Platform?

[Hortonworks Data Platform (HDP)](https://hortonworks.com/products/data-platforms/hdp/) is a widely popular massively scalable platform for storing, processing and analyzing large volumes of data. HDP is used in a variety of indutries from medical, to insurance to financial, to see [various HDP solutions on their website](https://hortonworks.com/solutions/). HDP consists of the essential set of Apache Hadoop projects including MapReduce, Hadoop Distributed File System (HDFS), HCatalog, Pig, Hive, HBase, Zookeeper and Ambari. Check out the image below to see what Apache Hadoop projects go into any given HDP release. More detail can be found for each of these projects by going to [Apache Hadoop's documentation](http://hadoop.apache.org/)
![](images/hdp_arch.png)

For our code pattern we focused on three components: Apache Spark, Search, HDFS, and Livy.

#### Apache Spark

[Apache Spark](http://spark.apache.org) is where event data is first loaded into and then it's machine learning library (MLlib) is used to train a collaborative filtering model. The model data is eventually stored and indexed into HDP Search by way of a Spark connector.

#### HDFS

[HDFS](https://hortonworks.com/apache/hdfs/) is used to store project data sets and is processed by Spark in a distributed fashion to do normal and ML transformations.

#### Livy

[Apache Livy](https://livy.incubator.apache.org/) is a service that enables easy interaction with a Spark cluster over a REST interface.

## How can I get started?

* Try the code pattern out. Check it out by going directly to our [GitHub repo](https://github.com/IBM/sms-spam-filter-using-hortonworks). The code pattern will walk the user through configuring HDP, Python library setup, running the notebook, and lastly interpretting the results.

* Want to see the notebook results directly? Use [NBViewer](http://nbviewer.jupyter.org/github/IBM/sms-spam-filter-using-hortonworks/blob/master/notebooks/Spam%20Filter%20using%20Scikit%20learn%20on%20remote%20spark.jupyter.ipynb) to view one of our code pattern notebooks.

* Keep an eye on [IBM Code](https://developer.ibm.com/code/patterns/) for more HDP related patterns!

### Read more: 

* https://hortonworks.com/blog/exciting-data-science-experience-hdp/
* https://hortonworks.com/blog/teaming-data-ibm-hortonworks-broaden-relationship/