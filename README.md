# Warning

Author is practicing readme-driven-development. Most of this doesn't exist. :)

# Repo Health

The open source community needs tooling for improving and monitoring the health of projects. Repo Health aims to provide guidelines for what makes an open source project healthy. Open Source contributors can use these guidelines to improve the quality of their project, and people looking at software can get insight on the robustness of a project. Progress can be measured over time, and the data can be used in choosing between two similar open source projects.


# Usage

Any of the following

* Go to http://repohealth.com and enter the github repo to check. It will scan the repo and provide a report for you

* Want your users to see the health of your repo?

```
[![Build Status](http://cdn.repohealth.com/status_images/github/$username/$project)](http://repohealth.com/repos/github/$username/$project)
```	
This will display the current health score for this repo. Great for your project's README page! For example, the current health of this repo:

![This repo has a health score of 80. Click to see full report](http://i.imgur.com/vhJIb.png)

#### Other options

* Use the API at http://repohealth.com/api 
* Clone this repo and run it locally
	`node report.js --repo $repo`
* Run a copy of repohealth.com yourself (clone this repo and run `node site.js`)


# Health Report Factors
Quality is highly subjective. Stylistic differences abound. The challenge to this project is to identify a set of common best practices that open source projects should have, and make recommendations so that their project is better. This will likely result in spirited debates over the definition of best practices, but that's part of the fun. :)

**Important note**: This isn't absolute.  Just because one project has a longer commit history than another project doesn't mean it's better code. By using a little pattern recognition, we can identify elements that make a repository better.


### All projects

##### Static analysis

Check the repo to see if the following files exist. Note that repo health will try to find them in common locations, or the [configuration file](#configuration-file) can be used to point it to alternate locations.

If these are not found, recommendations will be made along with suggestions and examples.

* README file exists and is at least x characters long
* LICENSE file exists
* .gitignore exists and lists out common temp files
	* .swp (vim)
	* .DS_Store (mac)
* .editorconfig
	* Code follows spacing rules 
* History/Changelog
* Getting Started/Usage/Example code/Demo
* Code passes a static processor (the appropriate config file is found, such as .jshintrc)
* Some automated build tool (Make, grunt, Rake, etc.)
* Contributors listed 
* TODOs/roadmap
* Dependencies/Requirements
* Using (people using the project)
* Separate tags/branches for releases
* Documentation (doc folder or wiki)
	* How much is enough? ratio to code? 

##### Community health

See how healthy the project is by gauging community involvement

* Last commit (actively maintained?)
* Number of committers (one man show or )
* Number of watchers
* Number of forks
* Issues/Support
	* Percent of issues with a response from a committer
	* Average time to first issue response
	* Average time to close an issue
* Pull requests
	* Percent of pull requests responded to
	* Average time to first pull request response
	* Percent of pull requests merged
* A mailing list
* Maturity (time since first commit, number of commits)
* Stack Overflow (via SO tag set in config. More project health than just repo health.)
	* Number of tagged questions
	* Unanswered / Total Tagged
	* Number of answerers (http://stackoverflow.com/tags/[TAG]/topusers)
	* Answerers / Askers


##### Tests
* Automated tests on every commit (look for travis to be set up)

### Language specific

##### node.js
* Project is on npm
* package.json
    * Valid...
    * Folders match package.json spec
        * doc
        * src
        * lib
        * test
        * dist

##### python
* Project on pypi
* requirements.pip

##### perl
* Project is on cpan
* "use strict"

Your favorite language not listed? Please add it!

### Configuration
If no repohealth configuration file is found and no project type is specified, it tries to determine the project type dynamically. 

If a repohealth configuration file is found (`.repo-health.json` in the project root), then the contributors can specify a different configuration than the default. For example, to let repo-health know that the `README` is actually called `read_me`:

```
{
	"files": {
		"README": "read_me"
	}
}
```

To see a sample configuration file, check out [this repository's .repo-health.json](.repo_health) file. To view the default configuration files, see [/languages/](languages/).

# TODO

#### API
* Add a repo to be scanned
* Trigger a scan
* Get details about repo health
* Get history of repo health
* Get previous health
* Serve up an image with the current score, #A-F report card style?

#### repohealth.com

* Input a repo, it will scan it and report back
* Last x repos' scanned
* Hall of shame/fame
* Track history score of repo over time
* See the health of popular projects (jQuery, backbone, yeoman)

