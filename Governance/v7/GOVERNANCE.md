# Project Tick Governance v7, 08 May 2026

<!--

Copyright (C) 2026 Project Tick

This Project Tick Management Document is an official governance document of Project Tick. It may be freely
distributed in its original, unmodified form. Modification of this document is not permitted for official
use. Only Project Tick may issue modified versions, which will be released under a new version identifier
and archived accordingly. Any third-party modifications must not be presented, distributed, or referenced
as an official Project Tick document. In such cases, the document must be renamed, and all references to
the Project Tick name, branding, and trademarks must be removed or clearly distinguished to avoid confusion.

-->

Welcome to Project Tick!

This document discusses the Project Tick ecosystem, repository management methods, and governance structure. With Project Tick Governance v6, the Monorepo model has been replaced with a PolyRepo model.

## Management

Project Tick's CI/CD requirements can be viewed via GitHub Actions; the NameSpace AND instance can be accessed via GitLab™ Self-Managed at [git.projecttick.org/project-tick/][6]. Upon entering the NameSpace, you will be greeted by a README file summarizing the process. As of April 29th, Project Tick has completely discontinued the use of Pull Requests (PR). Even without a Pull Request, you can easily use your repository rights and open a Merge Request (MR) through GitLab using GitHub OAuth or a personal account. All you need to do is open a MR immediately after submitting a commit (even if it's a draft). This allows you to test your commit in every aspect with CI. In short, we are now more free and our workflows are now repository-independent. Project Tick also has a GitLab™ Self Managed Enterprise Edition OSS Ultimate subscription. This simplifies both the CI/CD processes and makes our work easier. As of May 6th, Project Tick has officially abandoned the monorepo structure. The new structure is open. We call this the polyrepo structure. Each sub-project has its own repository. Hierarchy is more easily managed with GitLab's Subgroup feature. You will be able to understand the hierarchy both here and on the namespace entry page.

### Merge Request Model

As mentioned above, you submit an MR, it's reviewed, CI/CD is run, and if your results are successful, your commits are included directly into the main stream in their pure form via a merge commit.

### Maintainer model

Maintainers are responsible for maintaining the project folder located in the CODEOWNERS in the root directory. How to become a Maintainer? If you're wondering how to manage and improve your project folder according to Project Tick standards, our model is quite simple. You contribute long-term, and if deemed appropriate, your name is assigned to the necessary files in this folder, making you an administrator. Dear Maintainers, we expect you to treat contributors well and respectfully in accordance with the Code of Conduct. Please do your best to do so. With GitLab, you now have even more freedom. You can conduct your work comfortably and openly. After all, Github completely ties our hands.  As the Software Freedom Conservancy says: Give Up Github!

### Repository Model

Our repositories are not continuously and actively cloned to any platform. However, we use GitHub's Foreman system for CI/CD checks. With our Foreman system, we can easily test Merge Requests created in our own GitLab. In doing so, we have made workflows as repository-independent as possible, except for "secrets". Tons of projects like MeshMC, MNV, and Json++ can now be tested thanks to Foreman. Of course, we must also give credit to Flathub; we forked their "vorarbeiter" project, so we thank them. "Copyright (C) 2025 Flathub". As of May 6th, we are ending our mirroring efforts on Github and Codeberg. Because Github and Codeberg are now hindering us. To ensure CI/CD updates continue, the `project-tick/infra/github-actions` repository is mirrored to the `project-tick/project-tick` target on GitHub. If the URLs are broken, they need to be fixed; this is not our responsibility (except for our URLs). TL;DR: Go to git.projecttick.org, create an account, fork the repository(s), commit, open a merge request, run CI/CD, make sure it's successful, and we'll check and merge it. It's that simple.

### Decision-Making Model

The decision-making mechanism is entirely under the control of the highest-ranking person, [Mehmet Samet Duman][1]. He reviews and merges Merge Requests approved by maintainers. If a maintainer uses their veto power and this does not pass Mehmet Samet Duman's approval, the PR is unconditionally closed. However, if you think this is unfair, you can send a complaint to <projecttick@projecttick.org> with the [ISSUE] tag. Of course, a maintainer does not always have the right to use their veto power, but that does not mean they can never use it.

### Patch Acceptance Model

Your MRs undergo rigorous testing via CI/CD. Then, the maintainer of the relevant domain reviews the patch, and if the patch makes sense and doesn't contain bad code, the administrator bot calls @project-tick/maintainers using "bot, ping admins" command. He approves, and the patch is merged, which is very simple. Actually, quite simple. Maintainers can request fixes in patches, and if you approve the request and make the necessary changes, your chances of approval increase. Conversely, if you reject it without a solid reason, the administrator has veto power. Bad code means putting excessive effort into making things easier that could be done faster. Don't bloat your codebases to be more visible or show off on Gitblame. For example, if there is more than one administrator in a domain, a folder and a top-level administrator can be in the same project; a vote is held with +1 or -1 votes, and the one with the most votes prevails. For example, you made a change to the tests in the MNV folder and submitted a Merge Request (MR). The MR is reviewed by the maintainers, and if one maintainer requests a change and another agrees, all warehouse maintainers are called to vote on the MR. However, each maintainer reserves the right not to vote. In case of a tie, the final decision is made by the BDFL.

### Commit & Sign-off Model

Commits are made according to the DCO standard, meaning they are Signed-off-by. If DCO is not used, the MR bot will throw an error, and if this error is not corrected, the patch will be rejected. Please describe the actions you take in your commits in detail using the Header, Body, and Footer sections. We are trying to approximate the Conventional commits standard. Please try to adapt your commits accordingly.

### Inactive Maintainers Model

If a maintainer is unavailable, their position will be vacated. Maintainers, please let us know if you are leaving your post, are tired, or going on vacation. A maintainer can be offline for a maximum of 75 days if they don't have a valid reason or health issue. If a maintainer resigns or is dismissed, BDFL will replace the maintainer.

### Bug Control Model

Your bug reports will be received [here][4] or Project repositories. If you have any questions or issues regarding development, you can contact us via [GitLab Work Items][4]. Your bug reports will now be handled here.

### Project Tick SSO Model

Project Tick SSO uses the Keycloak infrastructure and helps you manage all your operations on projecttick.org or projecttick.net. We have prepared 4 OAuth mechanisms; Github, GitLab SaaS, Microsoft and Google. You can create an account with these infrastructures or via email. Our website now has an SSO infrastructure instead of its own form. This will save you from account confusion, don't worry. Go ahead and create an account [Here][3]. You can manage your account from there.

### Release & Versioning Model

In our versioning model, each project has its own version, and when a project is updated, a "prefixed" tag is created in its repository. The format is productname-VERSION-optionalsuffix. For example, when MNV version 10.0.4 is released, a prefixed tag is created. This model creates continuity by constantly updating the code without breaking it; if you are experiencing problems with this, you can use the latest LTS snapshot we have released. Or, if you find a bug, you can report it [here][4] or Project Repositories. Our beta versions are now available; however, our beta versions only provide source code instead of binary (executable file).

### Security Model

#### How to report

If you discover a security vulnerability, please report it via email:

- [`projecttick@projecttick.org`](mailto:projecttick@projecttick.org)

#### What to include

When submitting a report, please include:

- Steps to reproduce the issue
- Expected and actual behavior
- Affected versions
- Logs or crash reports if available

### Licensing & REUSE Compliance Model

We place great importance on SPDX. We actively define the REUSE system in both the lefthook of our Bootstrap scripts and perform full scans with CI/CD. Currently, there are no issues with the REUSE lint, but we require that any new files you create include SPDX-FileCopyrightText, SPDX-FileContributor, and SPDX-License-Identifier because, as mentioned at the beginning, SPDX is one of the most important components of the license identifier, and many distros currently prioritize the presence of SPDX headers in their source code.

### AI Usage Model

Don't worry! We're not jealous of you using AI, but we don't support it, nor are we against it. Use AI, but know its limits.

- AI should never, ever use the `Signed-off-by` tag.
- Don't send AI code without reviewing it and making necessary adjustments.
- The use of the `Assisted-by` tag is mandatory. If understood, the Maintainer gains the right to veto.
- Manage AI with contextually appropriate and well-written prompts. For example, a prompt should be at least 150 words long and contain detailed logic. Otherwise, AI, or LLMs, won't fit your context and will babble. - Use a memory bank system, but never put these memory banks in a repository. If necessary, temporarily add them to `.gitignore`, and if the Assistant gets frustrated because it can't see them, politely explain it to them.

### Source of Truth Model

The official Project Tick group and instance can be accessed [here]. Remember, we have no affiliation with GitHub (except for CI/CD). However, when these conditions are met – that is, when we have independent CI/CD machines – full independence will be achieved and this issue will be resolved to some extent. We are thinking of you and you can be sure that we will act accordingly. We returned to GitHub due to CI/CD restrictions and configurations, and decided that GitLab was not suitable for us. GitLab's contribution threshold is a bit high, and it is difficult for contributors to reach us, but let's not deny them their due. But you might ask, "Didn't the contribution space increase even more when you left GitLab SaaS and moved to your own infrastructure?" Don't worry. We returned to GitLab SM, thinking, "Why not?" Joking aside, thanks to Foreman, we can solve the CI/CD issue in Merge Requests. We have completely abandoned Mailman, Gitolite, CGit, Gitweb, Forgejo, and Bugzilla. Now we are all in one place. We are also abandoning GitHub entirely, except for CI/CD, due to the frustrating issues it has been causing recently. You can open your PRs as MRs, [and your Issues as Work Items in GitLab][4].

### PolyRepo Model

Project Tick has completely switched from the MonoRepo model to a PolyRepo model as of May 6th. The MonoRepo model made sense to us on GitHub because it allowed us to create repositories under the .org name without subgroups. That's no longer the case. Each project has its own repository, logo, and description; each subgroup has its own README, description, and repositories. Currently, the most repository is in the "Projects" subgroup, the entry point for Project Tick projects, as of May 6th. However, this number may increase over time, but a decrease is not expected.

### Mirror's Deprecation WARNING

Project Tick has discontinued mirroring services since transitioning to a polyrepo structure, specifically with Governance v6, except for github-actions and/or some exceptional repositories. The Project-Tick/Project-Tick repository on Github will remain to allow Foreman to handle CI/CD services, but its content will no longer be available. The mirrored locations are: Github, Gitlab Saas, Codeberg and Repo.or.cz.

### Labeling Model

### Subproject Boundaries

Each project makes its own decisions. We are in this Polyrepo structure. However, there are differences between the folder maintainer and the project maintainer. Project Maintainer:

```json
Project Tick
├── branding
├── documentation
├── governance
│   └── governancedoc
├── infra
│   ├── actions-images
│   ├── foreman
│   ├── github-actions
│   └── merge-action
├── legal
├── meta
│   ├── launcher
│   └── upstream
├── projects
│   ├── cgit
│   ├── classparser
│   ├── cmark
│   ├── corebinutils
│   ├── forgewrapper
│   ├── ganalytics
│   ├── genqrcode
│   ├── hooks
│   ├── iconfix
│   ├── imagesplusplus
│   ├── javacheck
│   ├── javalauncher
│   ├── jsonplusplus
│   ├── katabasis
│   ├── libnbtplusplus
│   ├── localpeer
│   ├── meshmc
│   ├── meta
│   ├── mnv
│   ├── neozip
│   ├── optional-bare
│   ├── rainbow
│   ├── scripts
│   ├── systeminfo
│   ├── tomlplusplus
│   └── xz-embedded
├── repositories
│   └── flatpak
├── statics
│   └── sfiles
└── website
```

As seen above, it generally manages one of the 16+ projects. However, the Folder Maintainer is only responsible for one folder within the 16+ projects. If there are interdependent projects among these 16+ projects, technical decisions must be made in a way that does not disrupt other products or in agreement with other project maintainers. Nothing should be broken here. Maintainers, we hope you know your place.

## Disclaimer

GITLAB is a trademark of GitLab Inc. in the United States and other countries and regions

[1]: https://github.com/YongDo-Hyun
[2]: https://github.com/project-tick/project-tick.git
[3]: https://id.projecttick.net/realms/projecttick/account
[4]: https://git.projecttick.org/groups/project-tick/-/work_items
[5]: https://git.projecttick.org/project-tick/governance/governancedoc/-/blob/master/GOVERNANCE.md#merge-request-model
[6]: https://git.projecttick.org/project-tick/
