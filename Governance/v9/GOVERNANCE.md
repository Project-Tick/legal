# Project Tick Governance v9, 23 June 2026

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

This document discusses the Project Tick ecosystem, repository management methods, and governance structure. Please note that Project Tick is an Umbrella project and is fully open to external project submissions. So, please register your projects [here][1]! Project Tick is a group dedicated to developing fully open-source projects, in addition to being an infrastructure project. It has no dependencies.

## Management

Project Tick's CI/CD requirements can be viewed via GitHub Actions and GitLab CI; the NameSpace and instance are accessible via GitLab™ Self-managed at [git.projecttick.org/project-tick/][2]. When you enter the NameSpace, you will find a README file outlining the process. This is a different world from GitHub. Remember, even without a Pull Request, you can easily exercise your rights in your repository and open a Merge Request (MR) via GitLab. All you have to do is open an MR immediately after submitting a commit (even if it's a draft). This allows you to test your commit in every aspect with CI. In short, we were always free. But now we are even freer, and our workflows are now repository-independent. This ensures the highest level of security. Each sub-project has its own repository. The hierarchy is more easily managed with GitLab's Subgroup feature. You will be able to understand the hierarchy both here and on the namespace homepage. GitLab is a structure that allows us to manage security controls, nested structures from a single top-down perspective, and to directly name any project or subgroup regardless of logo and path. Therefore, we always support GitLab and are fully behind it. You can reach Project Tick via [Help Desk][3].

### Merge Request Model

As mentioned above, you submit an MR. The authorities in that area review the files you've modified. If they deem it appropriate, they approve it. However, if they deem it inappropriate, they always have the right to reject it. Remember, we work here voluntarily and don't even accept donations. Please be tolerant of time discrepancies and delays, because that's the spirit of Open Source. We work asynchronously. After fulfilling the maintainer's requests, or if your code is already good and the pipeline is successful, your commits are consolidated into a single commit (merge train if available, otherwise direct merge) and included in the main branch with an additional merge commit. If you want to appear in the ChangeLog, you can check the Release Model and Changelog Model.

### Maintainer model

Maintainers are responsible for maintaining the project folder located in CODEOWNERS in the root directory. How to become a Maintainer? If you're wondering how to manage and develop your project folder according to Project Tick standards, our model is quite simple. You contribute long-term, and if deemed appropriate, your name is assigned to the necessary files in this folder, thus making you an administrator. If you don't want to bother with all that because you're busy, develop a project yourself and register with Project Tick. Dear Maintainers, we expect you to treat contributors well and respectfully in accordance with the Code of Conduct. Please do your best to do so. With GitLab, you now have even more freedom. You can conduct your work comfortably and openly. Ultimately, Github completely ties our hands. It hands over our code to LLMs. Even though we are open to LLMs, our code should remain with us. As the Software Freedom Conservancy says: Give Up Github! GitHub is inhumane. It simply binds us to itself stubbornly, and it continues to do so.

### Repository Model

Our repositories aren't constantly and actively cloned to any platform. However, we use GitHub's Actions and our Foreman system for CI/CD checks. With our Foreman system, we can easily test Merge Requests created in GitLab. In doing so, we've made workflows as independent of the repository as possible, except for "secrets". Many projects like MeshMC, MNV, and Json++ can now be tested thanks to Foreman. Of course, we should also thank Flathub; we were inspired by their "vorarbeiter" project. We forked it initially, then rewrote it with Ruby on Rails to counter the slowness of Python, so we thank them for giving us this inspiration. TL;DR: Go to git.projecttick.org, create an account, fork the repository(s), commit, open a merge request, run the CI/CD, make sure it's successful, and we'll check and merge. It's that simple.

### Decision-Making Model

The decision-making mechanism is entirely under the control of the highest-ranking person, [Mehmet Samet Duman][4]. He reviews and merges Merge Requests approved by Maintainers. If a maintainer uses their veto power and this does not pass Mehmet Samet Duman's approval, the PR is unconditionally closed. However, if you think this is unfair, you can send a complaint to <projecttick@projecttick.org> with the tag [ISSUE]. Of course, a maintainer does not always have the right to use their veto power, but that does not mean they can never use it.

### Merge Request Acceptance Model

Your MRs undergo rigorous testing via CI/CD. Then, the maintainer of the relevant domain reviews the patch, and if the patch makes sense and doesn't contain bad code, they approve it, and the MR is merged. It's actually quite simple. Maintainers can request fixes in patches, and if you approve the request and make the necessary changes, your chances of approval increase. Conversely, if you reject it without a solid reason, the administrator has veto power. Bad code means putting excessive effort into things that could be done faster. Don't bloat your codebases to be more visible or show off on Gitblame. For example, if there are multiple administrators in a domain, a folder and a top-level administrator might be in the same project; a vote is held with +1 or -1 votes, and the one with the most votes wins. For example, you made a change to the tests in the MNV project and submitted a Merge Request (MR). The MR is reviewed by maintainers, and if one maintainer requests a change and another accepts it, all repository maintainers are called to vote on the MR. However, each maintainer reserves the right not to vote. In case of a tie, the final decision will be made by the BDFL.

### Commit & Sign-off Model

Commits are made according to the DCO standard, meaning they are signed with Signed-off-by. If DCO is not used, Foreman will return an error, and if this error is not corrected, mr will be rejected. Please describe the actions you take in your commits in detail using the Header, Body, and Footer sections. We are trying to approximate the Conventional commits standard. Please try to adapt your commits accordingly.

### Inactive Maintainers Model

If a maintainer is unavailable, their position will be vacated. Maintainers, please let us know if you are leaving your post, are tired, or going on vacation. A maintainer can be offline for a maximum of 75 days if they don't have a valid reason or health issue. If a maintainer resigns or is dismissed, BDFL will replace the maintainer.

### Bug Control Model

Your bug reports will be received [here][5] or Project repositories. If you have any questions or issues regarding development, you can contact us via [GitLab Work Items][5]. Your bug reports will now be handled here.

### Project Tick SSO Model

Project Tick SSO uses the Keycloak infrastructure and helps you manage all your operations on projecttick.org or projecttick.net. We have prepared 4 OAuth mechanisms; Github, GitLab SaaS, Microsoft and Google. You can create an account with these infrastructures or via email. Our website now has an SSO infrastructure instead of its own form. This will save you from account confusion, don't worry. Go ahead and create an account [Here][6]. You can manage your account from there.

### Release & Versioning Model

In our versioning model, each project has its own version, and when a project is updated, a tag is created in its repository. The format is vX.Y.Z-suffix. For example, when MNV version 10.0.4 is released, a tag is created. This model creates continuity by constantly updating the code without breaking it; if you are experiencing problems with this, you can use the latest LTS snapshot we have released. Or if you find a bug, you can report it [here][5] or from the Project Repositories. Our beta versions are now available; however, our beta versions only provide source code instead of binary (executable file).

### Security Model

#### How to report

If you discover a security vulnerability, please report it via email:

- [`projecttick@projecttick.org`][7]

#### What to include

When submitting a report, please include:

- Steps to reproduce the issue
- Expected and actual behavior
- Affected versions
- Logs or crash reports if available

### Licensing & REUSE Compliance Model

We place great importance on SPDX. We actively define the REUSE system in both the lefthook of our Bootstrap scripts and perform full scans with CI/CD. Currently, there are no issues with the REUSE lint, but we require that any new files you create include SPDX-FileCopyrightText, SPDX-FileContributor, and SPDX-License-Identifier because, as mentioned at the beginning, SPDX is one of the most important components of the license identifier, and many distros currently prioritize the presence of SPDX headers in their source code.

### AI Usage Model

Don't worry! We don't begrudge you using AI, in fact, we now support it, not oppose it. Use AI, but know its limits.

- AI should never, ever use the `Signed-off-by` tag without your approval.
- Don't send AI code without reviewing it and making necessary adjustments.
- Manage AI with contextually appropriate and well-written prompts. For example, a prompt might be around 150 words long, but it should contain detailed logic. Otherwise, the AI ​​or LLMs will not fit your context and will babble. - Use a memory bank system, but never put these memory banks in a repository. If necessary, temporarily add them to `.gitignore`, and if the Assistant gets frustrated because it can't see them, explain it to it gently.

### Source of Truth Model

The official Project Tick group can be accessed [here][2]. Remember, we have no connection with GitHub (except for CI/CD). However, when these conditions are met – that is, when we have independent CI/CD machines – full independence will be achieved and this issue will be resolved to some extent. We are thinking of you and you can be sure that we will act accordingly. Thanks to Foreman, we are able to solve the CI/CD issue in Merge Requests. Now we are all in one place. Also, we are completely abandoning GitHub except for CI/CD due to the frustrating issues it has caused recently. You can open your PRs as MRs, [and your Issues as Work Items in GitLab][5].

### Labeling Model

Our labeling model is designed to be uncomplicated. We try to use every tag with scoped and a number in front of it as much as possible. Our labels have a certain order. If we have to mention,

```text
1.os::
2.type::
3.area::
4.with::
5.ci::
6.topic::
7.workflow::
8.has::
9.needs::
10.severity::
11.priority::
```

The structure you see above dominates.

### Foreman

Foreman is a developer-friendly platform. It's a massive monolith capable of running workflows from a GitHub repository, pulling and storing logs from workflows, writing pipeline status and external status checks to MR, and managing release processes. It operates by connecting to a user via a token, and then to a group, project, or system hook. It can write pipelines, display commands with "bot, help," sign CLAs, and update dependencies. It also includes a website and dashboard. It can securely manage our release processes and assign both beta and stable tags when the time comes.

### Changelog Model

Changelogs are generated using the trailers you specify in your commits.

### Release Model

The release model in Project Tick is quite clear. A stable tag is released on the 3rd Wednesday of each month, and a beta tag every week. The release follows each tag on the 3rd Thursday of each month. However, distribution to package managers can take until the 3rd Sunday of each month. Our tags are released as vX.Y.Z.

### Subproject Boundaries

Each project makes its own decisions. We are in this Polyrepo structure. However, there are differences between the folder maintainer and the project maintainer. Project Maintainer:

```text
Project Tick HQ
├── Community (ID: 17)
│   ├── Community Lab (ID: 128)
│   ├── Community Projects (ID: 127)
│   ├── Contributable Forks (ID: 129)
│   │   └── Project Tick (ID: 130)
│   │       └── Projects (ID: 131)
│   │           └── MeshMC [meshmc]
│   └── Onboarding [onboarding]
├── DevOps (ID: 19)
├── DevSecOps (ID: 20)
├── Developers (ID: 21)
│   └── MeshMC (ID: 40)
│       └── Plugins (ID: 96)
│           ├── All GA Plugins (ID: 107)
│           └── Staging (ID: 108)
│               └── All Non GA Plugins (ID: 112)
├── GitOps (ID: 22)
├── Governance (ID: 23)
│   └── Governance Document [governancedoc]
├── Infra (ID: 25)
│   ├── K8s (ID: 50)
│   │   └── Configs [configs]
│   ├── Vendored (ID: 51)
│   │   ├── forgejo (ID: 98)
│   │   │   └── forgejo [forgejo]
│   │   └── go-gitea (ID: 99)
│   │       └── gitea [gitea]
│   ├── Foreman [foreman]
│   ├── Gitea [gitea]
│   ├── ForgeJo [forgejo]
│   ├── Foreman 2.0 [foreman-2.0]
│   ├── Foreman 1.0 - Python [foreman-1.0]
│   ├── Actions Images [actions-images]
│   ├── Merge Action [merge-action]
│   └── GitHub Actions [github-actions]
├── Initiative (ID: 119)
│   └── Systematic Engineering (ID: 120)
│       └── Conditional Systems (ID: 121)
│           └── Lab (ID: 122)
│               └── Forks (ID: 123)
│                   └── Project Tick (ID: 124)
│                       └── Projects (ID: 125)
│                           └── MeshMC [meshmc]
├── Internal (ID: 26)
├── Maintainers (ID: 28)
├── Meta (ID: 27)
│   ├── Upstream [upstream]
│   └── Launcher [launcher]
├── Packaging (ID: 30)
│   └── ppm-pkgs [ppm-pkgs]
├── Private (ID: 29)
├── Projects (ID: 31)
│   ├── Libraries (ID: 89)
│   │   └── Vendored (ID: 102)
│   │       └── zlib-ng (ID: 110)
│   │           └── zlib-ng [zlib-ng]
│   ├── Vendored (ID: 90)
│   ├── Pen [pen]
│   ├── MeshMC [meshmc]
│   ├── MNV [mnv]
│   ├── CGit [cgit]
│   ├── NeoZIP [neozip]
│   ├── Images++ [imagesplusplus]
│   ├── ClassParser [classparser]
│   ├── CMark [cmark]
│   ├── CoreBinutils [corebinutils]
│   ├── ForgeWrapper [forgewrapper]
│   ├── GAnalytics [ganalytics]
│   ├── GenQRCode [genqrcode]
│   ├── IconFIX [iconfix]
│   ├── Hooks [hooks]
│   ├── JavaCheck [javacheck]
│   ├── JavaLauncher [javalauncher]
│   ├── Json++ [jsonplusplus]
│   ├── Katabasis [katabasis]
│   ├── LibNBT++ [libnbtplusplus]
│   ├── LocalPeer [localpeer]
│   ├── Optional Bare [optional-bare]
│   ├── MeshMC Meta [meta]
│   ├── RainBOW [rainbow]
│   ├── Toml++ [tomlplusplus]
│   ├── scripts [scripts]
│   ├── SystemINFO [systeminfo]
│   └── XZEmbedded [xz-embedded]
├── Release (ID: 33)
│   └── Deploy (ID: 88)
│       └── Tags (ID: 101)
├── Repositories (ID: 32)
├── Service (ID: 34)
│   └── desk (ID: 94)
│       └── Help Desk [help-desk]
├── Statics (ID: 35)
│   └── sFiles [sfiles]
├── Technical Writing (ID: 118)
│   └── Handbook (ID: 24)
│       ├── Governance (ID: 53)
│       ├── Legal (ID: 52)
│       ├── Libraries (ID: 54)
│       ├── Projects (ID: 55)
│       ├── Services (ID: 56)
│       │   └── Infra (ID: 100)
│       └── Systems (ID: 57)
├── Translations (ID: 37)
│   └── Project Tick ORG (ID: 95)
│       └── Projects (ID: 105)
│           └── meshmc [meshmc]
├── UppFinna Technologies (ID: 36)
├── Vendored (ID: 38)
├── triage-reports [triage-reports]
├── Release Tracking [release-tracking]
├── ppm [ppm]
├── gitlab-profile [gitlab-profile]
├── Documentation [documentation]
├── Project Tick Development Kit [pdk]
├── Branding [branding]
└── Legal [legal]
```

As seen above, it generally manages one of the 16+ projects. However, the Folder Maintainer is only responsible for one folder within the 16+ projects. If there are interdependent projects among these 16+ projects, technical decisions must be made in a way that does not disrupt other products or in agreement with other project maintainers.

## Disclaimer

GITLAB is a trademark of GitLab Inc. in the United States and other countries and regions

[1]: https://git.projecttick.org/project-tick/community/onboarding/-/work_items
[2]: https://git.projecttick.org/project-tick
[3]: https://git.projecttick.org/project-tick/service/desk/help-desk/-/work_items
[4]: https://git.projecttick.org/YongDo-Hyun
[5]: https://git.projecttick.org/groups/project-tick/-/work_items
[6]: https://id.projecttick.net/realms/projecttick/account
[7]: mailto:projecttick@projecttick.org
