---
jupyter:
  jupytext:
    text_representation:
      extension: .md
      format_name: myst
      format_version: '1.1'
      jupytext_version: 1.1.0
  kernelspec:
    display_name: Python 3
    language: python
    name: python3
---

+++ {"slideshow": {"slide_type": "slide"}}

# Whirlwind tour of teaching with Jupyter, autograding & Azure

## Learnings from the ACSE MSc

### Gerard Gorman <g.gorman@ic.ac.uk>
### James Percival <j.percival@ic.ac.uk>

+++ {"slideshow": {"slide_type": "slide"}}

# Health warning

### This is an interactive talk - login and follow along. We are even giving you an assessment as part of this talk ;-)
### Nothing is written in stone: Reflects work practice in the ACSE MSc for the last two years. Constantly evolving as technology constantly moving.
### Debate, comments, collaboration etc welcome.

+++ {"slideshow": {"slide_type": "slide"}}

## Overview of what we are covering

- [JupyterHub](https://jupyter.org/hub)
- [GitHub Classroom](https://classroom.github.com/) for distribution/submission coding assessments
- Autograding Python with [okpy](https://okpy.org/)
- [Visual Studio Code (VS Code)](https://code.visualstudio.com/). 
- E-infrastructure on [Azure Cloud](https://azure.microsoft.com/en-gb/)
- Plagiarism detection

+++ {"slideshow": {"slide_type": "subslide"}}

# Glossary 
For simplicity we include a short glossary. It is Azure centric simply because that is the provider we have been using - but most of the technologies listed are open source and cross-platform.
- VM's, [virtual machines running on Cloud](https://azure.microsoft.com/en-us/services/virtual-machines/)
- DSVM, [Data Science Virtual Machine](https://azure.microsoft.com/en-us/services/virtual-machines/data-science-virtual-machines/): VM for both Windows and Linux with lots of commonly used packages preinstalled/preconfigured (full list in link provided).
- [Azure Lab Services](https://labs.azure.com/): think college computer lab on a LAN; key advantage is that it is a turnkey solution that's straightforward to budget.
- [Azure Kubernetes Service (AKS)](https://docs.microsoft.com/en-us/azure/aks/): Azures flavour of [kubernetes](https://kubernetes.io/ orchestration) system for automating computer application deployment, scaling, and management. 

+++ {"slideshow": {"slide_type": "subslide"}}

- JupyterHub - multi-user version of Jupyter notebook designed for companies, classrooms and research labs
- Jupyter Notebooks - web-based interactive computational environment for creating Jupyter notebook documents.
- JupyterLab - next-generation user interface. Can open several notebooks, files, terminal as tabs in the same window. Offers of an IDE-like experience.
- Visual Studio Code is a free source-code editor made by Microsoft for Windows, Linux and macOS. Cross-language, cross-platform, *lots* of features including Live Sharing.

+++ {"slideshow": {"slide_type": "slide"}}

# Follow along: Create a GitHub account
- We are using GitHub to handle authentication so you need to have a GitHub account.
  - Using Software Carpentry (designed for novices) to train students on how to use GitHub: http://swcarpentry.github.io/git-novice/
  - Also using GitHub authentication for our Azure e-infrastructure because we were running into too many barriers with Service Principles when using College's Active Directory. Only an issue if you are creating your own infrastructure rather than the colleges.
  - Nice side effect: we can set up access to pre-sessional material for offer holders in advance of them having an ICT account.
  - Pain point: we have to create a lookup table to map GitHub username to College username.

+++ {"slideshow": {"slide_type": "slide"}}

# Follow along: Login to JupyterHub 
- Log onto our JupyterHub server using your GitHub account - https://acse-jhub-testing.westeurope.cloudapp.azure.com/hub/login
  - In this case set up with AKS.
  - This can be a little flaky (Kubernetes takes lots of tweaking - one of the reasons we are happy for ICT to take ownership); you may have to wait ~10mins if you are a new user as it allocates disk space etc for you. If you get 'Spawn failed: Timeout' then refresh your page (took 3 tries for me this morning).
  - Did not use Azure Labs here because the last time we checked it was non-trivial to get port 80 forwarded - we believe this is an upcoming feature.
  - Can also provision JupyterHub with a single 'fat' VM. Works fine for small classes but it does not scale! Often use this approach for conference tutorials etc.

+++ {"slideshow": {"slide_type": "slide"}}

# Follow along: Get your assignment from GitHub Classroom <WIP>
- GitHub Classroom - follow the link and accept the assignment... https://classroom.github.com/a/g4jAQPKr
- This will create a unique repo for *your* assignment under the GitHub org we have created for this talk.
  - Pro-tip: Create a new org for each year of the course (or module as we quickly end up with thousands of repositories within that org).
- Copy the repo URL; go back to your JupyterHub window; click new->Terminal; git clone <your-unique-assignment-repo>; return to previous JupyterHub tab and you will see the new folder listed; click to open.

+++ {"slideshow": {"slide_type": "slide"}}

## Jupyter/Jupyterhub

  - Azure Kubernetes Service (AKS) - scalable
  - Azure Labs - turn key
  - Fat VM - Short lead time

+++ {"slideshow": {"slide_type": "subslide"}}

  - Using IC AAD vs GitHub for authentication. 
    - Many other authenticators exist
  - Can run multiple environments on one Jupyterhub instance  
  
+++ {"slideshow": {"slide_type": "slide"}}

## Autograding Do's

Be *very* specific and beware of the [Barometer question](https://en.wikipedia.org/wiki/Barometer_question):
  - Treat the first few assignments as training students to become autograding-aware. 
  - Provide skeleton code, API'd and variable names so you can actually write tests, eg `assert result(life) == 42`.
    - Given the chance students will 'astonish' you in their ability not to follow the problem specification.
  - Stress capitalisation.
  - Floating-point comparisons and use of norms.
  - Test your tests (ideally set up CI - currently using GitHub actions).
  - Need to break assessments into carefully defined steps to refine the granularity of feedback and measure of learning outcomes.

+++ {"slideshow": {"slide_type": "subslide"}}

## Autograding Don'ts

- Don't use plots/figures as basis of tests.
- Don't send marks without a human in the loop.
- Don't have monolithic questions.
- Don't use as sole basis for assessment. Algorithms can go wrong...just look at A-level feasico. 

+++ {"slideshow": {"slide_type": "slide"}}

## Part II - Labs & VS Code

- We'll now do a (non-hands on) demo with an Azure Lab instead.
- <https://labs.azure.com/>
- Lab setup is *not* instant (can be a couple of hours with some interaction)
- Ditto for resizing
- Hand out specific sized VM with copy of template machine

+++ {"slideshow": {"slide_type": "subslide"}}

Key Features:
- Email out invitations/ see your audience
- Schedule core events
- Quota of extra time outside events
- Windows (RDP) & Linux (RDP & SSH) templates 

+++ {"slideshow": {"slide_type": "subslide"}}

- We'll connect to a copy of the Linux DSVM (need SSH)
- Demonstrate a workaround to get to a Jupyter notebook in the browser
- Demonstrate connecting with VS Code instead.

+++ {"slideshow": {"slide_type": "slide"}}

## Visual Studio Code

<https://code.visualstudio.com/>
- Free, lightweight cross-platform code editor with IDE-like features
- *Not* Visual Studio (no compilers)
- Extensible, configurable
- Large community doing support
- Supports remote editing and collaboration tools

+++ {"slideshow": {"slide_type": "slide"}}

## What we covered

- JupyterHub
- GitHub Classroom for distribution/submission coding assessments
- Autograding Python with `okpy`
- VS Code/IDE 
- e-infrastructure on Azure Cloud

+++ {"slideshow": {"slide_type": "subslide"}}

## What we haven't done yet - need to discuss

- Plagiarism detection
- Blackboard integration
- Other languages (will be similar for many, but not all Jupyter kernels)

+++ {"slideshow": {"slide_type": "slide"}}

## Jupyterbook

<https://jupyterbook.org/>

- Mix multiple notebooks up into organised webpages
- Text (markdown) & code (notebooks)
- Run live code (mybinder.org & Thebelab)
- Instant links to jupyterhub
- Easy to serve on GitHub Pages

Example created by ESE undergrad Student Shapers <https://primer-computational-mathematics.github.io>


+++ {"slideshow": {"slide_type": "slide"}}

## Questions?


+++ {"slideshow": {"slide_type": "slide"}}