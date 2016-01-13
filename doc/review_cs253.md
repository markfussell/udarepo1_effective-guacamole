
This is some feedback on course cs253: Web Development.  

Clearly the teacher knows how to build a web application, with credentials including two well-known services web services.  He 
talks very clearly and writes quite neatly, and was never factually wrong (that I noticed) in his description.  I liked the 
idea of the office hours to go over issues, although ultimately that should be fed back into the original materials.

I think a big issue is that the materials are not layered, 'completed cleanly', and the minimal needed for the goals of the week and class.
The first week covered HTTP and HTML but these are really completely separable topics and by completing each one sufficiently
(and for basic Web Development) the student would more easily digest and retain the information.  HTML can be edited and rendered from
simple local files (file:...) or a static website like GitHub.  Understanding HTML (at least 'basic output') doesn't require understanding 
HTTP user-agents, GAE, or really much of anything beyond URLs being links/references to something else.  

And similarly, understanding HTTP does not require thinking that much about the content (HTML or JSON or image or ...) resource that is retrieved.  And again, user-agents and GAE are extraneous and confusing. 

A second example is to have a dynamic web site requires some kind of 'persistence' but using python for that persistence
initially is easier to understand (is more empowering) than bringing in SQL and non-SQL databases (including some very unusual 
ones like Dynamo).  And worrying about the query plan and performance of a database is only valuable when you can build
something that works.

If the units and weeks were more easily digested, I think the course would be much more effective.


A second issue is "Quo Vadimus" through this whole process.  Where are we going?  How close are we to getting there?
A common way of designing applications is to start with wire-frames (or sample HTML), try to get them to be dynamic,
and then try to make them persistent, authenticated, etc.  This would likely work well for at least the first three weeks.  

I think if every week it was obvious where you were going (say starting with a WordPress.com
blog as an example) and that you were week-on-week getting closer to that, it would be easier to learn and stickier for the student.


Advanced topics like SQL query plans could be in bonus materials that might help make a successor course (performant web sites) 
or later week's materials easier.  




