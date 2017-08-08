# GitHub Classroom Guide for Teachers

This is a guide for using GitHub Classroom to assist or run your class. We are using GitHub Classroom for a class where the assignments are primarily, if not all, R Markdown files. However, this guide should be applicable to most classes.


### Setting up GitHub Classroom:
1. If you plan on repeating the class in future semesters, set up a "master" classroom organization. If you are teaching a class titled "Intro to Statistics", we recommend calling this organization intro-statistics-master, or something similar. We use this organization to host all assignments that will be used in the current and future versions of the class. Each assignment should be its own repository. When using GitHub classroom to send out assignments, we can use repositories from this organization as starter code. If changes need to be made for future years, you can change the repository in the organization without affecting the current version of the class. If you want the assignments to be private, you can apply for an educational discount that will grant the organization unlimited repositories. Go to https://github.com/settings/connections/applications/64a051cf1598b9f0658f and grant GitHub Classroom organizational access to the master organization.

2. Make an organization for the current version of the class titled something similar to intro-statistics-fall-2017 (or whatever semester and year you're teaching). Apply again for unlimited private repositories for this class so that individual assignments can be private (preventing potential cheating). Go to https://classroom.github.com/classrooms and click "New classroom" in the upper right corner. Choose the class you are currently teaching. Note that this step will have to be repeated for each semester.

3. Add all other teachers and TAs to the organizations as owners.

4. Go to the current year's version of the classroom organization. Under settings, go to member privileges. Change Default repository permission to "none" and save these changes. This will make it so that students cannot change non-assignment repositories in the organization.

5. (Optional). You can manually add students via email to the organization as members. However, once you send out (and they accept) the first assignment, they should automatically join the organization.

### Sending out individual assignments
1. Make the assignment repo in the master organization. This can include all starter code, data, etc... Be smart about naming your repository. Remember, there are no spaces allowed in GitHub repository names. We recommend using the dash "-" to separate words and numbers. A couple examples of assignment names we have used are "test-assignment" and "unit-1-assignment-1". 

2. Go to https://classroom.github.com/classrooms and click on the current class organization. Click new assignment, then create an individual assignment.

3. Use the repistory name as the assignment name. You can skip the "Your assignment repository prefix" box, as this should automatically be filled in with the assignment name.

4. Unless you want all of the students to see each others' assignments, click Private repository.

5. Add the assignment from your master organization as the starter code. You will probably have to manually type out the organization name for all available repositories to show up.

6. Copy the invitation link and send this out in a mass email to students. Students should now be able to click on this link to set up the repository.
