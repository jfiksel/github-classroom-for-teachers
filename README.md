# GitHub Classroom Guide for Teachers

This is a guide for using GitHub Classroom to assist or run your class. We are using GitHub Classroom for a class where the assignments are primarily, if not all, R Markdown files. However, this guide should be applicable to most classes.


### Setting up GitHub Classroom:
1. If you plan on repeating the class in future semesters, set up a "master" classroom organization. If you are teaching a class titled "Intro to Statistics", we recommend calling this organization intro-statistics-master, or something similar. We use this organization to host all assignments that will be used in the current and future versions of the class. Each assignment should be its own repository. When using GitHub classroom to send out assignments, we can use repositories from this organization as starter code. If changes need to be made for future years, you can change the repository in the organization without affecting the current version of the class. If you want the assignments to be private, you can apply for an educational discount that will grant the organization unlimited repositories. Go to https://github.com/settings/connections/applications/64a051cf1598b9f0658f and grant GitHub Classroom organizational access to the master organization.

2. Make an organization for the current version of the class titled something similar to intro-statistics-fall-2017 (or whatever semester and year you're teaching). Apply again for unlimited private repositories for this class so that individual assignments can be private (preventing potential cheating). Go to https://classroom.github.com/classrooms and click "New classroom" in the upper right corner. Choose the class you are currently teaching. Note that this step will have to be repeated for each semester.

3. Add all other teachers and TAs to the organizations as owners.

4. Go to the current year's version of the classroom organization. Under settings, go to member privileges. Change Default repository permission to "none" and save these changes. This will make it so that students cannot change non-assignment repositories in the organization.

5. Add students to the organization. You can do in this two ways. The first is by manually adding students via email to the organization as members. This can be quite a pain if you have more than 5 students in your class. Luckily, once you send out (and they accept) the first assignment, they will be added to the organization as outside collaborators. If you go to the People section of the organization and click on Outside collaborators, you should be able to click on the gear icon next to each student's name and click invite to organization. Once the students accept the invitation, they should be removed from the outside collaborator panel into the members panel. While this is still some work, you do have a nice way of checking who has accepted the invitation.

6. (Optional). Edit the README.md of the current year's classroom organization to be the class syllabus. You can also add a repository with non-assignment material so that the students can clone and pull changes in an organized manner throughout the semester. We are a little bit worried about creating merge-conflicts with this system and are thinking about solutions to avoid this. 

### Sending out individual assignments
1. Make the assignment repo in the master organization. This can include all starter code, data, etc... Be smart about naming your repository. Remember, there are no spaces allowed in GitHub repository names. We recommend using the dash "-" to separate words and numbers. A couple examples of assignment names we have used are "test-assignment" and "unit-1-assignment-1". 

2. Go to https://classroom.github.com/classrooms and click on the current class organization. Click new assignment, then create an individual assignment.

3. Use the repistory name as the assignment name. You can skip the "Your assignment repository prefix" box, as this should automatically be filled in with the assignment name.

4. Unless you want all of the students to see each others' assignments, click Private repository.

5. Add the assignment from your master organization as the starter code. You will probably have to manually type out the organization name for all available repositories to show up.

6. Copy the invitation link and send this out in a mass email to students. Students should now be able to click on this link to set up the repository.

### Grading assignments
Before I go into the steps on how to do this, I'll mention that this step will probably vary from teacher-to-teacher. If you have a different workflow from us, please feel free to share how you grade assignments from GitHub!

1. Have a directory for the class in your local computer. Inside of this directory, I would recommend making a directory titled something similar to `homework-grading`. The way we will use this directory is that we have a shell script (more on this in the next step) that will create a sub-directory within the `homework-grading` named after an assignment prefix. The script then automatically clones all of the students' repos for this assignment into the directory. 


2. Navigate to the `homework-grading` directory. The shell scripts we will be using are from https://github.com/konzy/mass_clone. You can either clone this repo, or my forked version https://github.com/jfiksel/mass_clone, into the `homework-grading` directory. Currently, my forked version allows you to pull changes in from a student's repository if they have made changes after your initial cloning. At this point, your directory structure should be as follows:

```
class-fall-2017
│   
│    
│
└───homework-grading
    │   
    │   
    │
    └───mass_clone
        │   README.me
        │   clone_all.sh
        |   clone_all_helper_example.sh
        |   push_all.sh
```

3. Edit the `clone_all_helper_example.sh` script so that your class specific organization and your username replaces the default settings in the organization and username fields

4. When you are ready to edit all the assignments, go to the terminal and navigate to the `mass_clone` repository. Type in `./clone_all_helper_example.sh`. You can then enter in the assignment prefix when prompted (or just type `./clone_all_helper_example.sh assignment-prefix`). For example, if we are grading `unit-1-homework-1`, then I would type in 
`./clone_all_helper_example.sh unit-1-homework-1`. You will then be prompted to enter your GitHub password. Unfortunately, you will have to enter in the password everytime you do this step, even if you have SSH set up (which you should!). Your directory structure will now look like this

```
class-fall-2017
│   
│    
│
└───homework-grading
    │   
    │   
    │
    |────mass_clone
    |    │   README.me
    |    │   clone_all.sh
    |    |   clone_all_helper_example.sh
    |    |   push_all.sh
    |
    |
    |
    |────unit-1-homework-1
         |
         |
         |----unit-1-homework-1-student1
         |   
         |            
         |----unit-1-homework-1-student2            
         |        
                  .
                  .
                  .
         |
         |----unit-1-homework-1-studentN
```

5. You can either edit all the assignments by typing comments into their documents, or by adding a new file with comments to each student's repository. If there is only one document that students will be editing, then it's possible to open up each student's document, put in your changes, and then save. We don't recommend putting in the official assignment grade into your comments due to privacy issues. 

6. After saving (you have to save!) your changes and/or new files, navigate to the `mass_clone` directory. Type in `./push_all.sh assignment-prefix`. This script will commit all of your changes with the same commit message ("Graded <date> <time>"), and then push all of the changes back to the students' repositories. 

### Additional resources
* https://classroom.github.com/videos
