---
layout: post
tagline: 
title: Perfect tests. Is an Utopia?. No, is an obligation.
tags : [Continuous Delivery, QA, Quality Assurance, Aseguramiento de la calidad, test, prueba, cucumber, jenkins]
comments : true
language : en
date: "2015-04-11"
spanish_url: "2015-04-11-perfeccion-en-tests-automaticos-utopia-no-obligacion.html"
---
{% include JB/setup %}

_First of all, sorry for my English. Any correction is well received._

Any company that generates a software product should devote their efforts to have the most refined [Continuous Delivery](http://en.wikipedia.org/wiki/Continuous_delivery) system possible. For this one word is key: `automation` ... but I leave the topic of automation for another moment, today I'm going to focus on the responsibility of the QA department and its duty to be demanding with the results of its automated tests . Let us start with a couple of premises for a more concrete example:

* Using [Cucumber](https://cukes.info) for the definition / implementation of automated tests.
* The use of [Jenkins](https://jenkins-ci.org/) and [Publish pretty cucumber-jvm reports on Jenkins](https://github.com/masterthought/jenkins-cucumber-jvm-reports -plugin-java) plugin.

We started ...

### QA team birth

At the beginning of a QA equipment, the number of automated tests is zero, therefore the said tests are carried out manually which implies a considerably waste of time (and therefore a waste of money).

### First automated tests

After some time (if using Scrum, it's likely that this period of time is a sprint) the first automated tests are created. These tests are automatically launched after the generation of the X.Y.Z version of the software product that we are developing.

In this case, and for clarity with counts, we assume that 10 automatic tests are released and the result is that there aren't any errors. Perfect!

Example (report without errors):

<p align="center">
<img src="../../images/cucumber_no_error.jpg" title="Report without errors" width="600" height="450">
</p>

### Automating
 
Time passes and the QA team offers 100 automated tests. Version X.Y.(Z + n) is now released and we run the test suite. The result is that 10% of the tests fail (10 tests of 90).

In this situation the tests are analyzed and different things can happen:

1. The test is poorly designed or implemented, there is a `bug` in the test. ACTION ** ** -> create a bug (Jira, Bugzilla, Mantis, etc.) and correct it as soon as possible.
2. The test is successful, the software has a `bug`. ACTION ** ** -> create a bug (Jira, Bugzilla, Mantis, etc.) and correct it as soon as possible.
3. The test is meaningless because the covered functionality has disappeared. ACTION ** ** -> Remove the test.
4. The test is correct, but the environment, where the tests have been launched, has performance problems, communications ... or perhaps timeout values ​​are correct for production environment but are too demanding for the develoment environment.

Example (report with errors):

<p align="center">
<img src="../../images/cucumber_errores.jpg" title="Report without errors" width="600" height="550">
</p>


The fourth point is the whichone we must be careful because, if you do nothing in any way, could lead to an undesirable situation: the software is getting the QA certification without 100% of past tests. This is dangerous because if repeatedly taken as good executions of the tests with 10% of errors, this could lead to a false sense that with 90% of tests accepted the software is right, and this long-term trend in the time is inadmissible because a few months later...

The automation of tests is growing quickly into the QA team and we have now 10,000 automated tests. But as we have been relaxed the requirements of the tests we are still assuming that 10% of errors is OK... and this means that there are 1000 tests that fail!!.

Therefore, given the situation of point 4, I think that a reaction is needed. I show you some options:

* The test disappears because we cannot ensure that the result is conclusive.
* The test disappears for environment X. It was decided that in this environment the test can not be executed with minimum guarantees.
* The test is modified to suit for the environment X. The parameter settings would be adjusted for each environment. To obtain these values, benchmarks could be made in the different environments and the results would indicate relationships like "The answers of database in environment A is 3 times faster than the environment B".
* Environment is modified (more CPUs, more memory, improved communications, changes in the database, etc.) in the way that the test can achieve its goal.

Thus QA department only certify when their tests are 100% correct. No doubts. No exceptional considerations that can be dangerous and lead to a false sense of stability in the presence of errors.

So I consider that **seeking perfection in tests (get a 100% correct results) should not be utopian, but an obligation**, not only by the QA team in their tests, but also by part of any programmer in their unit tests, or integration tests, etc.

In this aspect in [amplía)))](http://www.amplia.es) (the company where I'm currently working) we are lucky to have a [meticulous person as QA manager](https : //www.linkedin.com/pub/jorge-rodriguez/8/a81/2ba/s).

Are your tests 100% OK? Can you think of any more valid actions for point 4? Do you have any situation that cause an erroneous test?