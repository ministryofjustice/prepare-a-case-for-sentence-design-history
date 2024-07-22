# HMPPS Preprare a case for sentence design history

A place documenting the design history of the prepare a case for service.

## About out design history

[It uses the GOV.UK Design History](https://github.com/DFE-Digital/govuk-design-history) to build and show pages using [Eleventy](https://www.11ty.dev). All pages are made in markdown, [find out how to use markdown](https://www.markdownguide.org/basic-syntax/).

You can find the [HMPPS Prepare a case for sentence prototype here](https://github.com/ministryofjustice/hmpps-prepare-a-case-prototype).

### Accessing the live HMPPS Prepare a case for sentence service

The live service is accessed by NDelius, you may need to [speak to their support team on Slack](https://moj.enterprise.slack.com/archives/C6C1KGRME) to get access to the live service.
If you need to access pre-production then you must have SC clearance, speak to your delivery lead if you need this.

### Purpose of this repo

To:

- create pages of screenshots to document designs
- link to relevant prototypes where applicable
- document designs using the [GOV.UK Design System](https://design-system.service.gov.uk/)
- make designs shareable and linkable

## Installation and getting started

### Running the prototype

1. Clone the prototype to your local machine
2. Install npm once so that the prototype can be run `npm install`
3. Start the prototype `npm start`
4. View `http://localhost:8080/` in your browser


### Making your own design history

This is a very rough guide that is most likely incomplete/sufficient for someone new to make their own design history. You could try and mitigate some of this by roping in a developer to help set things up.

1. Clone a version of this design history
2. Find the folder in your file explorer
3. Rename the folder to something sensible like MY-SERVICE-NAME-design-history
4. Make sure you can see hidden files (MAC press COMMAND + SHIFT + .
5. Delete the .git file and folder so that its not using GitHub source control
6. In Terminal, navigate to this folder and type in `git init` and hit enter to initialise GitHub source control
7. Set the remote URL to your new repo and to use SSH with the command `git remote set-url origin git@github.com:OWNER/REPOSITORY.git`. Make sure you replace OWNER and REPOSITORY with the information for your repo
8. Add all the changes to a commit using `git add .` in terminal
9. Create a commit using `git commit -m First commit`
10. Push that commit to your repo and confirm the files have been uploaded
11. In Terminal run `npm install`
12. In Terminal run `npx @11ty/eleventy` to check everything installed correctly, it should suggest commands to install missing dependencies
13. In Terminal run `npm install govuk-frontend --save` to install GOVUK front end so that it looks like GDS site
14. In Terminal run `npm start` to get the site to build and run
15. View the site on the Access URLs shown in terminal this is usually `http://localhost:8080/` by default.
16. Check the site looks and works as expected
17. Set up your repo on Cloud platform so that you will have somewhere live to host the design history. [Follow this guide](https://user-guide.cloud-platform.service.justice.gov.uk/documentation/getting-started/prototype-kit.html#1-copy-clone-the-environments-repository). If you get stuck you can try reaching out to the [Cloud Platform team on Slack](https://moj.enterprise.slack.com/archives/C57UPMZLY).
18. Set up continuous deployment so that everytime you merge into the main branch the site is rebuilt and pushed live. You will need to amend `.github/workflows/cd-main.yaml`, `Dockerfile` and `kubernetes-deploy-main.tpl`

Problem with this guide, make a pull request or contact me directly. You can find me on Slack or email [richard.cooley@digital.justice.gov.uk](mailto:richard.cooley@digital.justice.gov.uk)
