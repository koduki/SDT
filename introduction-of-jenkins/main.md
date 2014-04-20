% Introduction of Jenkins.
% @koduki
% Apr 21, 2014

Agenda
================================================================================
- What is Jenkins?
- Jenkins gives us what? 
- How to use?
- Conclusion


What is Jenkins?
================================================================================
- Jenkins is a butler written by Java to help your work.
- This is very useful especially for CI(continuous integration).
- This tool execute build, test, deploy, analyze metrix, report... instead of you. 

What is Jenkins?
================================================================================
- Integrates with SCM(git, svn, cvs)
- Integrates with ant, maven, and shells(sh, bash, cmd...)
- Execute task timer or SCM event or manually
- This is bit similer job management tool(cron, A-AUTO, Systemwalker, Senju)

Jenkins gives us what? 
================================================================================

## Do you have these problems?
- Mistake build operation (e.g. You made JDK7 not JDK6 but module.
- Forgot send repot (e.g You've overslept.
- Too many requests of build and deploy!
- Build and test are OK in my environment, but others are failed.

Jenkins gives us what? 
================================================================================
\begin{center}
\fontsize{120px}{0pt}\selectfont
\textcolor{yellow}{Jenkins execute task on your behalf !}
\end{center}

Jenkins gives us what? 
================================================================================
## Our Case Study 01 : all branch build and test(continuous integration)
- Currently, all development branch are build and test once an hour.
- We can know commit or testdata mistake.
- Same time, we run sonar build. 
- We can know code metrix(readbirity, quality, coverage) every time!
- And important, this process is not required our time.

Jenkins gives us what? 
================================================================================
## Our Case Study 02 : deploy on stage environment
- We use deployment on stage environment.
- This is made of dependent tasks of 4.
	1. check out the latest code and build new module
	2. deploy new module
	3. activate new module
	4. undeploy old module
- If you do manualy this task, it's complexy.
- However, jenkins don't make mistake and don't complain.
- Because, he is a machine.

Jenkins gives us what? 
================================================================================
## Our Case Study 03 : send veracode report.
- We use veracode. This is Static Application Security Testing(SAST).
- This analysis is very long time. Usually, it's half or 1 day.
- A report will not be sent, if you are rest or forget execute. 
- However, jenkins don't forget and don't rest.
- Because, he is a machine.

Jenkins gives us what? 
================================================================================
\begin{center}
\fontsize{120px}{0pt}\selectfont
\textcolor{yellow}{Jenkins execute task on your behalf !}
\end{center}


How to use?
================================================================================
## Install
- Download war file from official site(http://jenkins-ci.org/)
- Execute jar

```sh
java -jar jenkins.war
```

- Access "http://localhost:8080"
- It's so easy!
- Of course, you can use our common environemnt. please tell me.

Conclusion
================================================================================
- Jenkins is a butler written by Java to help your work.
- This tool execute build, test, deploy, analyze metrix, report... instead of you. 
- A try is so easy!
```sh
java -jar jenkins.war
```
