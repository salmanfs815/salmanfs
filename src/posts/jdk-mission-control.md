---
layout: layouts/post.njk
title: JDK Mission Control
date: 2020-01-02T07:42:10.023Z
tags:
  - work
  - open-source
  - java
  - redhat
  - jmc
---
This was the project my team was working on during my coop at Red Hat in Toronto.
Formerly Java Mission Control, the tool was a proprietary offering in Oracle's Java subscription.
It was open-sourced by Oracle in early 2018 (just before the start of my internship) as JDK Mission Control (JMC).
It is now a project under the OpenJDK umbrella.

There was previously a similar open-source tool developed by the OpenJDK team at Red Hat called Thermostat.
Red Hat decided to focus their efforts on improving JMC rather than working on Thermostat since JMC was already the de facto industry standard.

A related project under OpenJDK is JDK Flight Recorder (JFR), formerly Java Flight Recorder.
This was also open-sourced along with JMC (OpenJDK 11+).
This is a feature that is internal to the JVM. It records events inside a JVM and saves them to a file.
In the event of a program crash, JMC can help diagnose the issue using data from the JFR file.
This is analogous to the black box or flight recorder in modern aircraft that records critical information about the plane to facilitate
investigations following aviation accidents.

Working on JMC was a very drastic change from previous projects I've worked on. First of all, the Java programming language was quite foreign to me.
Aside from a very rudimentary course in high school, I had little to no exposure to Java programming.
Given fluency in other programming langugages, syntax was fairly easy to learn.

One of things I did struggle with was understanding the project structure.
The organization of the various modules and the workings of Maven were difficult to grasp.
To add salt to the wounds, the project had a strange build mechanism whereby some of the required files were downloaded from
Maven Central only to be hosted locally so that another build tool could download from the local server to build some plugins.

JMC is built as an Eclipse plug-in. This means it is an Eclipse RCP application and many of the dependencies are core libraries in Eclipse.
This had pros and cons. The con was that it was difficult to follow a stacktrace without being lost deep in the weeds of Eclipse code.
The pro was that there was an entire team of Eclipse developers that I could also consult when trying to diagnose strange behaviour.
Regardless of what team one is on or what other projects one is occupied with, fellow Red Hatters were always willing to lend a hand.

I worked on a couple low-hanging fruit in the JIRA when I wasn't busy with packaging work (more on that below).

### First patch

The first patch I submitted was for [JMC-6118](https://hg.openjdk.java.net/jmc/jmc/rev/ecb68ef82eb7).
Since JMC was initially developed with Oracle JDK, there were some tests that assumed JFR features were available, even in JDK 8.
Naturally, these tests were failing with OpenJDK 8 was used for testing.

I modified some POM files to tell Maven to skip JFR-specific tests when running on OpenJDK versions without JFR.

### Some more patches

A few more of [my patches](https://hg.openjdk.java.net/jmc/jmc/log?rev=sasiddiq) were incorporated into the upstream JMC code,
addressing issues such as using the default Java when running on Linux and making some error messages more informative.
