gsywhgs
In Assignment2, we started with a discussion of the topic, a preliminary meeting on website design and how the group meetings would work. So we started to divide and record our work on Trello, in which all the members participated actively going in that direction. After that, we started deploying our site on Wordpress.

We first created a Wordpress domain name and set up a website. On the main page, we invited all team members to participate in the common Wordpress website to edit our project. From the plugins, we have also downloaded a plug-in called starter template, which allows us to better serve and edit our site.

At the beginning, we could not link to Wordpress well because of the network. After several attempts to link to VPN, we finally succeeded in linking to Wordpress.

For version control, we use the latest version to control and collaborate with our Wordpress. The linking problems, operational problems, and testing problems that can result from different versions are huge.

Also for testing and automation problems, every time we finished a project, each member of our team would test it to see if it was running properly or if there were any problems. Then we would make unified modifications, such as editing the website pictures, failing to upload them, and making incorrect sizes. Finally, integrate the website
GitHub Actions Setup
Provide crendentials for GitHub Actions to use when logging into the servers, add following to the GitHub Secrets:

PRODUCTION_HOST = IP address of production server

PRODUCTION_KEY = SSH private key of production server

PRODUCTION_USERNAME = username used for logging into production server

STAGING_HOST = IP address of staging server

STAGING_KEY = SSH private key of staging server

STAGING_USERNAME = username used for logging into staging server

Utilizing Staging Server
We don't want to introduce any unexpected bugs to the production Wordpress instance. Thus, any changes to the theme must be tested out on the staging server before the changes make their way into the production server. You can also create a branch and merge them back if you are making big changes to the theme.

The staging and production servers are hosted seperately in different servers, to ensure that there are no dependency conflits. When enough testing is done, the theme is ready to push to production server.

In order to the changes to the staging server, all you need to do is code on your local environment and push changes to the staging branch of the GitHub repository, as you would normally. GitHub Actions will take care of the deployment to the staging server.

Pushing to Production Server
When enough testing is done on the staging server and you are ready to deploy to the production site, create a pull request to merge the changes from the staging branch to the main branch. Then, GitHub Actions will automatically deploy the theme to the production server
