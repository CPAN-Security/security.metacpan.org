# A Simplified Open Source Supply Chain

* Community: CPAN Security Working Group
* Homepage: https://security.cpan.org
* Projects
    * CPAN Metadata & Software Bills of Materials
    * CPAN Security Outreach & Information
* Contact
	* Email: Salve J. Nilsen <sjn@oslo.pm>
	* Mastodon: @sjn@chaos.social

Below is an illustration showing the different roles that influence a typical Open Source supply chain. 

The purpose of this, is to establish effective narratives that can help people with these roles get a clear picture of what benefit SBOMs can play in their work, and for their downstream users.

```mermaid
stateDiagram-v2
    state "Author\nCustodian\nSteward" as author
    state "Distributor — Repository" as distributor_repo 
    state "Distributor — Language" as distributor_lang 
    state "Distributor — Package" as distributor_package
    state "Patcher" as patcher
    state "Packager" as packager
    state "Curator" as curator
    state "Developer" as developer
    state "Deployer" as deployer
    state "Scanner\nSecOps\nPentester" as scanner
    state "Consumer\nUser" as consumer
    state "Auditor" as auditor

	[*] --> ecosystem_author

	state "Author Environment" as ecosystem_author {
    	[*] --> author
    }

    author --> ecosystem_repo
    author --> ecosystem_lang

	note right of ecosystem_author
		Open Source Developer
	end note

    state "Language Ecosystem" as ecosystem_lang {
    	[*] --> distributor_lang
    }

	distributor_lang --> ecosystem_developer
	distributor_lang --> ecosystem_package

	state "Repository Ecosystem" as ecosystem_repo {
		[*] --> distributor_repo
	}

   	distributor_repo --> ecosystem_package
    distributor_repo --> ecosystem_developer

	state "Package Ecosystem" as ecosystem_package {
		[*] --> patcher
		[*] --> packager
    	patcher --> packager
    	packager --> curator
    	packager --> distributor_package
    	curator --> distributor_package
	}

	note right of ecosystem_package
		May have downstream
		package ecosystems
	end note

    distributor_package --> ecosystem_developer

	state "Developer Environment" as ecosystem_developer {
		[*] --> developer
	}

	note right of ecosystem_developer
		"Closed Source" Author
	end note

    developer --> ecosystem_prod

	state "Production Environment" as ecosystem_prod {
		[*] --> deployer
    	deployer --> scanner
    	deployer --> consumer
    	deployer --> auditor

	}

    developer --> [*]


```

# License

This is © Salve J. Nilsen <sjn@cpan.org>. Some rights reserved.
You may use, modify and share this file under the terms of the CC-BY-SA-4.0 license.
