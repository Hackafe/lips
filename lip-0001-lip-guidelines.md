```
  LIP: 0001-lip-guidelines
  Title: LIP Purpose and Guidelines
  Discussions: http://frm.hackafe.org/t/lip-lip-purpose-and-guidelines/441
  Status: Accepted
  Type: Process
  Created: 2015-12-25
```


**Content:**

1. Abstract
2. Motivation
3. Specification
	1. Terms Definitions
		* What is a LIP?
			- LIP Types
			- Structure of a successful LIP
			- LIP Head
			- LIP File Format
			- Auxiliary Files
	2. Actors
		1. LIP Author
		2. LIP Editors
	3. LIP Workflow
		1. Submitting a LIP
		2. LIP Editors Review
		3. LIP Resolution
4. Rationale
5. References and Footnotes


# 1. Abstract

This document describes the process of submitting proposals for improvements in the lab and decision making of the community.


# 2. Motivation

The purpose is to have a transparent and efficient mechanism for the lab to evolve and accommodate wider community of people gathering as many great ideas as possible.


# 3. Specification


## 3.1. Terms Definitions

### What is a LIP?

LIP stands for Lab Improvement Proposal. A LIP is a design document providing information to the lab community, or describing a new feature for lab or its processes or environment. The LIP should provide a concise description of the improvement and its rationale.

We intend LIPs to be the primary mechanisms for proposing major new features, for collecting community input on an issue, and for documenting the design decisions that have gone into the lab. The LIP author is responsible for building consensus within the community and documenting dissenting opinions.

Because the LIPs are maintained as text files in a versioned repository, their revision history is the historical record of the LIP.


#### LIP Types

There are two kinds of LIP:

- A Process LIP describes a process surrounding the lab, or proposes a change to (or an event in) a process. Examples include procedures, guidelines, changes to the decision-making process, and changes to the tools or environment used in running the lab. Any meta-LIP is also considered a Process LIP.

- An Informational LIP provides general guidelines or information to the lab community, but does not propose a new process. Informational LIPs do not necessarily represent a community consensus or recommendation, so members are free to ignore Informational LIPs or follow their advice.


#### Structure of a successful LIP

Each LIP should have the following parts:

0. **Preamble** - RFC 822 style headers containing meta-data about the LIP, including the LIP number, a short descriptive title (limited to a maximum of 44 characters), the nicknames, and optionally the contact info for each author, etc.

1. **Abstract** - a short (~200 word) description of the issue being addressed.

2. **Motivation** - The motivation is critical for LIPs that want to change the lab's processes. It should clearly explain why the existing process specification is inadequate to address the problem that the LIP solves. LIP submissions without sufficient motivation may be rejected outright.

3. **Specification** - The process specification should describe the actors and their actions in the steps of the process.

4. **Rationale** - The rationale fleshes out the specification by describing what motivated the design and why particular design decisions were made. It should describe alternate designs that were considered and related work, e.g. how the process works in other labs and OpenSource communities.
The rationale should provide evidence of consensus within the community and discuss important objections or concerns raised during discussion.

5. **Backwards Compatibility** - All LIPs that introduce backwards incompatibilities must include a section describing these incompatibilities and their severity. The LIP must explain how the author proposes to deal with these incompatibilities. LIP submissions without a sufficient backwards compatibility treatise may be rejected outright.


#### LIP Head

Each LIP must begin with an RFC 822 style head. The headers must appear in the following order. Headers marked with "*" are optional and are described below. All other headers are required.

```
  LIP: <LIP number>
  Title: <LIP title>
  Author: <list of authors' nicknames and optionally, email addresses>
* Discussions: <url to the forum thread>
  Status: <InVoting | Accepted | Rejected | Withdrawn | Superseded>
  Type: <Process | Informational>
  Created: <date created on, in ISO 8601 (yyyy-mm-dd) format>
* Replaces: <LIP number>
* Superseded-By: <LIP number>
  Resolution: <url>
```

The Author header lists the nicknames, and optionally the email addresses of all the authors/owners of the LIP. The format of the Author header value must be

```
ironsteel <address@dom.ain>
```

if the email address is included, and just

```
ironsteel
```

if the address is not given.

If there are multiple authors, each should be on a separate line following RFC 2822 continuation line conventions.

Discussions header will indicate the URL to the forum thread where the LIP is being discussed.

The Type header specifies the type of LIP: Process or Informational.

The Created header records the date that the LIP was assigned a number. It should be in yyyy-mm-dd format, e.g. 2001-08-14.

LIPs may have a Requires header, indicating the LIP numbers that this LIP depends on.

LIPs may also have a Superseded-By header indicating that a LIP has been rendered obsolete by a later document; the value is the number of the LIP that replaces the current document. The newer LIP must have a Replaces header containing the number of the LIP that it rendered obsolete.

The Resolution header contains a URL that points to the pronouncement about the LIP is made.


#### LIP File Format

LIPs should be written in markdown format. Image files should be included in a subdirectory for that LIP.


#### Auxiliary Files

LIPs may include auxiliary files such as diagrams. Such files must be named LIP-XXXX-Y.ext, where "XXXX" is the LIP number, "Y" is a serial number (starting at 1), and "ext" is replaced by the actual file extension (e.g. "png").


## 3.2. Actors

### 1. LIP Author

The LIP author (or authors) writes the LIP using the style and format described in this LIP, guides the discussions in the appropriate categories in the [forum](http://frm.hackafe.org/), and attempts to build community consensus around the idea.

Authors MUST NOT self assign numbers, but should use an alias such as "lip-ironsteel-some-workflow" which includes the author's nickname and the LIP subject.


### 2. LIP Editors

The LIP editors are individuals responsible for the administrative and editorial aspects of the LIP workflow:

- They assign LIP numbers and change their status.
- They correct any structure, grammar, spelling, or markup mistakes we see.

A LIP editor must be registered in the forum.

Many LIP authors are not git committers yet, so LIP editors do the commits for them.

All LIP-related correspondence should be sent (or CC'd) to lip_dot_editors_at_hackafe_dot_org.

The editors don't pass judgement on LIPs. They merely do the administrative & editorial part (which is generally a low volume task).


## 3.3. LIP Workflow

The workflow is:
<pre>
        ______________________
        |                    |
        V                    |
1. Submit a LIP -> 2. LIP Editors review -> 3. Resolution
</pre>

### 1. Submitting a LIP

The LIP process begins with a new idea for the lab. It is highly recommended that a single LIP contain a single key proposal or a new idea. The more focused the LIP, the more successful it tends to be. The LIP editor reserves the right to reject LIP proposals if they appear too unfocused or too broad. If in doubt, split your LIP into several well-focused ones.

**Step 0: Check the idea** (recommended)
The LIP author should first attempt to ascertain whether the idea is LIP-able. Posting to the [forum](http://frm.hackafe.org/) is the best way to go about this.

Vetting an idea publicly before going as far as writing a LIP is meant to save the potential author time. Many ideas have been brought forward for changing lab that have been rejected for various reasons. Asking the lab community first if an idea is original helps prevent too much time being spent on something that is guaranteed to be rejected based on prior discussions (searching the internet does not always do the trick). It also helps to make sure the idea is applicable to the entire community and not just the author. Just because an idea sounds good to the author does not mean it will work for most people in most areas where lab is used.

**Step 1: Publish a draft in the forum**
Once the author has asked the lab community as to whether an idea has any chance of acceptance, a draft LIP should be presented in the [forum](http://frm.hackafe.org/). This gives the author a chance to flesh out the draft LIP to make properly formatted, of high quality, and to address initial concerns about the proposal.

LIP authors are responsible for collecting community feedback on a LIP before submitting it for review. However, wherever possible, long open-ended discussions on public forums or mailing lists should be avoided. Strategies to keep the discussions efficient include: setting up a separate form thread for the topic, having the LIP author accept private comments in the early design phases, setting up a wiki page or git repository, etc. LIP authors should use their discretion here.

**Step 2: Submit for review**
When the LIP is ready for the repository, the author should submit it as a "pull request" to the [lab/lips](https://github.com/Hackafe/lips) repository on GitHub where it may get further feedback.

If the LIP author can not use git yet, then they should send their LIP to lip_dot_editors_at_hackafe_dot_org and a LIP editor will submit it as a "pull requests" for them.


### 2. LIP Editors Review

Once a "pull request" is submitted, the LIP editors have 48 hours to review the LIP.

For each new LIP that comes in the editors do the following:

1. Read the LIP to check if it is ready: sound and complete.
 - The ideas must make practical sense, even if they don't seem likely to be accepted.
 - The title should accurately describe the content.
2. Edit the LIP for language (spelling, grammar, sentence structure, etc.), markup.

The LIP must be written in LIP style as described in this LIP, else an editor will send it back without further regard until proper formatting rules are followed.

The LIP editors will not unreasonably deny a LIP. Reasons for denying LIP status include duplication of effort, being practically unsound, not providing proper motivation or addressing backwards compatibility, or not in keeping with the lab philosophy.

If no editor denies the LIP for 48 hours, then one of them will:

1. Merge the pull request.
2. Assign a LIP number (usually just the next available number, but sometimes it can be other) and give it status "InVoting".
3. List the LIP in [lab/lips/README.md](https://github.com/Hackafe/lips/blob/master/README.md).
4. Officially announce the new LIP and next steps in the forum.


### 3. LIP Resolution

The official announcement in the forum starts the voting on the LIP. The lab members have 72 hours to vote in the forum.

If the majority of the votes support the LIP, then it gets status "Accepted".
Else it is "Rejected". Perhaps after all is said and done it was not a good idea. It is still important to have a record of this fact.

In case the LIP author themselves has decided that the LIP is actually a bad idea, or has accepted that a competing proposal is a better alternative, then the LIP is put on status "Withdrawn".

LIPs can also be superseded by a different LIP, rendering the original obsolete with status "Superseded".

When a LIP status is changed, the Status header and Resolution header must be updated.


# 4. Rationale

The  members should be able to define how the lab functions.
The workflow of gathering proposals, reviewing them and decision-making described in this LIP follow these principles:

- The process is transparent on every step. All discusions and voting happen in the forum.
- There is no single point that can delay or stop the workflow. The LIP editors just help to put the things in order, but they don't judge. The editors are many, while just one is needed. So at any time any editor can do the task.
- The times for discussions, review and voting are enough for every interested to participate and in the same time doesn't delay a resolution.
- The members interested in a given LIP can participate actively, while the ones who are not - don't need to do anything.


# 5. References and Footnotes

[1] This document was derived heavily from Python's PEP-0001: <https://www.python.org/dev/peps/pep-0001>. In many places text was simply copied and modified.

