# Warning

Author is practicing readme-driven-development. Most of the this doesn't exist. :)

# Repo Health

As the open source community grows, we need tooling for monitoring the health of source code and it's repositories. This project aims to provide guidelines for what makes an open source project healthy. Open Source contributors can use these guidelines to improve the quality of their project, and people looking at software can get insight on the robustness of a project.

# Usage
* Go to http://repohealth.com and enter the github repo to check. It will scan the repo and provide a report for you
* Clone this repo and run it locally
	`node report.js --repo $repo`
* Run a copy of repohealth.com yourself (clone this repo and run `node site.js`)


# Health Report Factors
Quality is highly subjective. Stylistic differences abound. The challenge to this project is to identify a set of 

### Configuration
If no repohealth configuration file is found and no project type is specified, it tries to determine the project type dynamically. 

If a repohealth configuration file is found (`.repo-health.json` in the project root), then the contributors can specify a different configuration than the default. For example, to let repo-health know that the `README` is actually called `read_me`:

```
files
	README
		read_me
```

To see a sample configuration file, check out [this repository's .repo-health.json](.repo_health) file. To view the default configuration files, see [/configs/](configs/).

### All projects

##### Static analysis

* README file
* LICENSE
* .gitignore for common temp files
	* .swp (vim)
	* .DS_Store (mac)
* .editorconfig
	* Code follows spacing rules 
* History/Changelog
* Getting Started/Usage/Example code/Demo
* Code passes a static processor. that config file is found
* Some automated build tool (Make, grunt, Rake, etc.)
* Contributors listed somewhere
* TODOs/roadmap
* Dependencies/Requirements
* Using
* Separate tags/branches for releases
* Documentation (doc folder or wiki)
	* How much is enough? ratio to code? 

##### Community health

* Last commit (actively maintained?)
* Number of committers (one man show or )
* Number of watchers
* Number of forks
* Issues/Support
* A mailing list

##### Tests
* Automated tests on every commit


### Language specific

##### node.js
* package.json
* on npm
* Folders match package.json spec
	* doc
	* src
	* lib
	* test
	* dist
	
##### python
* pypi

##### node.js


Your favorite language not listed? Please add it!

## repohealth.com

#### Features 

* Input a repo, it will scan it and report back
* Last x repos' scanned
* Hall of shame/fame
* Track history of score