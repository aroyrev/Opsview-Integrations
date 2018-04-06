# How to upload your Opspack to GitHub

1. Create a new repository on GitHub

   ![Create new GitHub Repository](/docs/img/create_new_repo.png?raw=true)

2. Import into the new repository from the template repository which is located at: https://github.com/opsview/opspack-template

   ![Import Template Project](/docs/img/import_project.png?raw=true)

3. Clone the repository to your local directory. It should contain all the files from the template:

   ```
   git clone https://github.com/GBedenko/database-etcd.git
   ```

4. Replace the directory 'opspack-template' with your opspack folder

5. Travis CI (travis-ci.org) is used for testing and deploying an Opspack in GitHub.

    * Enable travis on your new repository

   ![Enable Travis builds](/docs/img/enable_travis.png?raw=true)

    * You also need to add a personal access token to your environment variables for the repository in Travis. The access token needs to have at least repo access. See following documentation: [Travis Environment Variables](https://docs.travis-ci.com/user/environment-variables)

   ![Add Access Token](/docs/img/add_access_token.png?raw=true)

6. Update the README.md file with information from the user facing documentation for your opspack. Also update the travis build which is linked in this file.

7. Push all the changes so far as initial commit:

   ```
      git add .
      git commit -m "Added Opspack source files"
      git push
   ```

8. When happy with the repository, make a release by running the following:

   ```
       git tag -a v1.0 -m "Opspack Release"
       git push --tags
   ```
9. Link your Opspack from the Opsview Integration main repository page
