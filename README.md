[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://github.com/dduzgun-security/github-self-hosted-runners">
    <img src="https://github.blog/wp-content/uploads/2019/08/DL-V2-LinkedIn_FB.png?fit=1200%2C630" alt="Logo" >
  </a>

  <h3 align="center">Github Self-Hosted Runners Configuration</h3>

  <p align="center">
    Guideline of best practices to follow to use Github Self-Hosted Runners in a secure way.
    <br />
    <br />
    <a href="https://github.com/dduzgun-security/github-self-hosted-runners/issues">Report an issue</a>
  </p>
</p>


## Table of contents

<!--ts-->
   * [About the project](#about-the-project)
   * [Confidentiality](#confidentiality)
      * [Using self-hosted runners only in trusted GitHub Actions](#using-self-hosted-runners-only-in-trusted-github-actions)
      * [Limit access to self-hosted runners](#limit-access-to-self-hosted-runners)
      * [Disable forks](#disable-forks)
      * [Run the self-hosted runner on hardened hosts only](#run-the-self-hosted-runner-on-hardened-hosts-only)
   * [Integrity](#integrity)
      * [Use the latest and greatest runner](#use-the-latest-and-greatest-runner)
   * [Availability](#availability)
      * [High availability](#high-availability)
      * [Automatically clear and remove workspaces](#automatically-clear-and-remove-workspaces)
   * [Authentication](#authentication)
      * [Secure the authentication token of the self-hosted runner](#secure-the-authentication-token-of-the-self-hosted-runner)
   * [Authorization](#authorization)
      * [Only use the technologies you need](#only-use-the-technologies-you-need)
   * [Audit](#audit)
   * [Checklist](#checklist)
   * [Support section](#support-section)
   * [Contributing](#contributing)
   * [License](#license)
   * [Contact](#contact)
<!--te-->

<!-- ABOUT THE PROJECT -->
## About the project
Looking for a guideline to configure your GitHub Self-Hosted Runners in a secure way? 

Here is a :fire: list of things to do!

<!-- CONFIDENTIALITY -->
## Confidentiality
##### Using self-hosted runners only in trusted GitHub Actions
Self-hosted runner are using the dedicated host as the runner. 
Only verified GitHub Actions must use self-hosted runners to reduce the use of a potential malicious open-source GitHub Action that migth access our pruvate network.

##### Limit access to self-hosted runners
Restrict the use of self-hosted runners to specific repositories only.  
https://docs.github.com/en/free-pro-team@latest/actions/hosting-your-own-runners/managing-access-to-self-hosted-runners-using-groups

##### Disable forks
Disable forks since forks of your public repository can potentially run dangerous code on your self-hosted runner machine by creating a pull request that executes the code in a workflow.

##### Run the self-hosted runner on hardened hosts only
The host of the self-hosted runner must be a hardened OS. 
Hardening of the OS is the act of configuring an OS securely, updating it, creating rules and policies to help govern the system in a secure manner, and removing unnecessary applications and services. This is done to minimize a computer OS's exposure to threats and to mitigate possible risk.  
https://www.cisecurity.org/cis-benchmarks/ 

<!-- INTEGRITY -->
## Integrity
##### Use the latest and greatest runner
Ensure that the host machine always uses the latest version of the self-hosted runner.  
https://github.com/actions/runner/releases/latest

![image](https://user-images.githubusercontent.com/59659739/100800872-2ffc4c80-33f5-11eb-8ed5-95b3a91d863a.png)


<!-- AVAILABILITY -->
## Availability
##### High availability
Since self-hosted runners are essential to talk with the internal network of an enterprise, they need to be highly available.  
https://github.com/philips-labs/terraform-aws-github-runner

##### Automatically clear and remove workspaces
Since the self-hosted runner clones the source code in a workspace, we need to ensure that this workspace doesn't get overpopulated and consumes all the available space of the host.

<!-- AUTHENTICATION -->
## Authentication
##### Secure the authentication token of the self-hosted runner
The authentication token used to configure the runner needs to be secured and restricted since it has write-access permissions on the repository.  
Using Hashicorp Vault may be a good solution for this.

<!-- AUTHORIZATION -->
## Authorization
##### Only use the technologies you need
Keep the self-hosted runner simple and authorize only the things you need. For exemple, if you don't need npm don't install it inside the runner.

<!-- AUDIT -->
## Audit
https://docs.github.com/en/free-pro-team@latest/actions/learn-github-actions/security-hardening-for-github-actions#auditing-github-actions-events

<!-- CHECKLIST -->
## Checklist
 - [ ] Using self-hosted runners only in trusted GitHub Actions
 - [ ] Limit access to self-hosted runners
 - [ ] Disable forks
 - [ ] Run the self-hosted runner on hardened hosts only
 - [ ] Use the latest and greatest runner
 - [ ] High Availability
 - [ ] Automatically clear and remove workspaces
 - [ ] Secure the authentication token of the self-hosted runner
 - [ ] Only use the technologies you need

<!-- SUPPORT SECTION -->
## Support section
[Github Enterprise Support](https://enterprise.github.com/support) offers very usefull assistance on everything you search. :+1:

* [Documentations](https://help.github.com/en)
* [Request creation](https://enterprise.githubsupport.com/hc/en-us/requests/new)

Also, GitHub offers a [Premium Support](https://help.github.com/en/github/working-with-github-support/about-github-premium-support-for-github-enterprise-cloud) with a 24/7 hours of operation availability time.

<!-- CONTRIBUTING -->
## Contributing
Contributions are what make the open source community such an amazing place to be learn, inspire, and create. Any contributions you make are **greatly appreciated**.

1. Fork the Project
2. Create your Feature Branch (`git checkout -b feature/AmazingFeature`)
3. Commit your Changes (`git add . && git commit -m 'Add some AmazingFeature'`)
4. Push to the Branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

<!-- LICENSE -->
## License
Distributed under the MIT License. See `LICENSE.txt` for more information.

<!-- CONTACT -->
## Contact
[Deniz Onur Duzgun](https://github.com/dduzgun-security)  
[Khalid Nazmus Sakib](https://github.com/knsakibnbc)

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/dduzgun-security/github-self-hosted-runners.svg?style=flat-square
[contributors-url]: https://github.com/dduzgun-security/github-self-hosted-runners/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/dduzgun-security/github-self-hosted-runners?style=flat-square
[forks-url]: https://github.com/dduzgun-security/github-self-hosted-runners/network/members
[stars-shield]: https://img.shields.io/github/stars/dduzgun-security/github-self-hosted-runners.svg?style=flat-square
[stars-url]: https://github.com/dduzgun-security/github-self-hosted-runners/stargazers
[issues-shield]: https://img.shields.io/github/issues/dduzgun-security/github-self-hosted-runners.svg?style=flat-square
[issues-url]: https://github.com/dduzgun-security/github-self-hosted-runners/issues
[license-shield]: https://img.shields.io/github/license/dduzgun-security/github-self-hosted-runners.svg?style=flat-square
[license-url]: https://github.com/dduzgun-security/github-self-hosted-runners/blob/master/LICENSE.txt
