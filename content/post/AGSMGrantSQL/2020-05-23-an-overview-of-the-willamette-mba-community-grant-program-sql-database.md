---
title: An Overview of the Willamette MBA Community Grant Program SQL Database
author: Zachary Dyne
date: '2020-05-23'
slug: agsmgrantssql
categories:
  - SQL
  - Data Engineering
  - MBA
tags:
  - SQL
  - Access
  - MBA
  - Willamette MBA Community Grant Program
subtitle: ''
summary: 'This post provides an overview of the SQL database I created for the Willamette MBA Community Grant Program during my MBA.'
authors: []
lastmod: '2020-05-23T10:28:44-07:00'
featured: no
image:
  caption: ''
  focal_point: ''
  preview_only: no
projects: []
---

One of my favorite courses I took during my time at Atkinson was *GSMDS5003: Data Engineering*, taught by the one and only Prof. Henry Bi. We not only learned how to write SQL code but also about the fundamentals of database design, including entity relational (ER) modeling, standardization, and normalization. Learning the structure of well designed databases made learning to retrieve data via SQL a fairly straitforward extension. The course's final project was to create a database of our own using Microsoft Access, so I decided to use this opportunity to solve a different problem I was dealing with: the information scattered throughout the Google Drive of the Willamette MBA Community Grant Program.

### Willamette MBA Community Grant Program

The [Willamette MBA Community Grant Program](https://www.agsmgrants.com/) is the only 100% student-administered grantmaking program in the US and provides funding opportunities for nonprofit or social service organizations serving Oregon's [Marion, Polk, and/or Yamhill counties](https://geology.com/county-map/oregon.shtml). As students facilitating multiple rounds of grantee applications bt reviewing organizational and operational metrics while following up on the results of projects from previous funding cycles, it was getting difficult to keep track of all of the information we needed. As the project manager and lead financial data analyst, the disorganization made creating tools for internal communication, financial statement analysis, and risk modeling particularly tedious. Additionally, because it is completely student-run, the program experiences 100% annual turnover, with the exception of the two faculty instructors. This makes organizing institutional knowledge all the more difficult yet essential. Seems like a problem an Access SQL database could solve!

### Database Overview

My goal in creating this database was to make it as flexable as possible to adapt to future itrations of the program. The Grant Program only just finished its fourth year and there are many things that could hypothetically happen that haven't yet. As such, the database seems a bit redundant (in SQL-talk: it has more many-to-many relationships than initally seems necessary). For example, an *EnrollIn* relationship needs its own table since it is hypothetically possible for a student to enroll in the course more than once (they coud be a JD/MBA or an MBA-for-Life student). If we just assumed that each student will enroll in the course only once, *EnrollIn* could just be a column in the *Student*  table. Feel free to check out the [full project description](https://drive.google.com/file/d/1rOdZmnAYQa-UH4V_KDCOjGDaF2aHaYjl/view?usp=sharing) for all of the database requirements.

While I can't share the content of many tables due to privacy reasons, I can share the database's relationship diagrams as a proof of concept. 

##### Entity Relation Model

[![ERD Model](/post\AGSMGrantSQL/2020-05-23-an-overview-of-the-willamette-mba-community-grant-program-sql-database_files/ERDModel.PNG)](/post\AGSMGrantSQL/2020-05-23-an-overview-of-the-willamette-mba-community-grant-program-sql-database_files/ERDModel.PNG)

#### Access Relational Diagram
[![Access Relational](/post\AGSMGrantSQL/2020-05-23-an-overview-of-the-willamette-mba-community-grant-program-sql-database_files/AccessRelation.PNG)](/post\AGSMGrantSQL/2020-05-23-an-overview-of-the-willamette-mba-community-grant-program-sql-database_files/AccessRelation.PNG)

#### Hey, it works!
Sample problem: *List the organization name, project name, description, and amount recieved for each project operated by an organization who has operate more than on project. Provide the list in descending order by amount.*

![Sample Code](/post/AGSMGrantSQL/2020-05-23-an-overview-of-the-willamette-mba-community-grant-program-sql-database_files/SampleCode.PNG)

![Sample Q](/post\AGSMGrantSQL/2020-05-23-an-overview-of-the-willamette-mba-community-grant-program-sql-database_files/SampleQ.PNG)

### Final Thoughts

I had a lot of fun working on this project since it combines two of my primary interests: data science and nonprofit management. Thank you to Prof. Henry Bi for your guidance and encouragement along the way! If you're interested to learn more about the Willamette MBA Community Grant Program, check out the recently published [2019-2020 Annual Report](https://static1.squarespace.com/static/5d96678c577c9008fd68696b/t/5eb30597c5e14117f3481700/1588790698192/WUMBA_PICI_Y4_AnnualReport2020.pdf)! 

