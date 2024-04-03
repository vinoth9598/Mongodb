# Mongodb


1.Find all the topics and tasks which are thought in the month of October :
       db.students.find({users:'student'},{topic:1,task:1});

2.Find all the company drives which appeared between 15 oct-2020 and 31-oct-2020:
            db.company_drives.find({
                $or: [{_date: { $gte: new Date("2020-10-15") } },{_date: { $lte: new Date("2020-10-31") } ]
            });

3.Find all the company drives and students who are appeared for the placement.
      -db.students.find({users : "student"},{component_drives : 1});

4.Find the number of problems solved by the user in codekata
      -db.students.find({users : "student"},{codekata : 1});

5.Find all the mentors with who has the mentee's count more than 15
      -db.students.find({ mentee_count: { $gt: 15 } });
      
6.Find the number of users who are absent and task is not submitted  between 15 oct-2020 and 31-oct-2020
      -db.students.find({users : "student"},{attendance :{ $elemMatch : {status : "A"}}},{task : { $eq : { task : "false" }}});







