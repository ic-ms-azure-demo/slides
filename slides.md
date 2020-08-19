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

# Whirlwind tour of teaching with Jupyter, autograding and Azure

## Learnings from the ACSE MSc

+++ {"slideshow": {"slide_type": "slide"}}

## Overview of what we are covering

- JupyterHub
- GitHub Classroom for distribution/submission coding assessments
- Autograding Python with `okpy`
- VS Code/IDE 
- e-infrastructure on Azure Cloud
- Plagarism detection

+++ {"slideshow": {"slide_type": "subslide"}}

# Terminology (Azure centric)

- VM - virtual machine (running on Cloud)
- DSVM - Data Science Virtual Machine (VM with lots of commonly used packages preinstalled)
- Azure Labs - think college computer lab on a LAN
- Azure Kubenetes Service (AKS): orchestration system for automating computer application deployment, scaling, and management. 
- JupyterHub - multi-user version of jupyter notebook designed for companies, classrooms and research labs
- Jupyter Notebooks - web-based interactive computational environment for creating Jupyter notebook documents.
- JupyterLab - next-generation user interface. Can open several notebooks, files, terminal as tabs in the same window. Offers of an IDE-like experience.
- Visual Studio Code is a free source-code editor made by Microsoft for Windows, Linux and macOS. Cross language, cross platform, *lots* of features including Live Sharing.

+++ {"slideshow": {"slide_type": "slide"}}

## Part II - to Jupyterhub

+++ {"slideshow": {"slide_type": "slide"}}
  - Azure Kubenetes Service (AKS)
  - Azure Labs
  - Fat VM

## Autograding Do's

+++ {"slideshow": {"slide_type": "subslide"}}

  - Using IC AAD vs GitHub for authentication.   
## Autograding Don'ts

+++ {"slideshow": {"slide_type": "slide"}}

## Part II - Labs & VS Code

+++ {"slideshow": {"slide_type": "slide"}}

## Questions?


- create through away org
- double check for bitrot on whatever platform
- create github classroom with invite list - set assignment 1.1
- use for our cluster https://acse-jhub-testing.westeurope.cloudapp.azure.com/

- Brief introduction
- Technology: github classroom, git, AKS (not using azure labs because jupyter currently non-trivial), Jupyter+python, autograding using okpy, authenitication using github (some legwork to associate two identies; also we don't like aad because it gives service principle nightmares) - missing: blackboard integration, currently using inhouse code. Cannot ssh to pods for AKS; cannot access jupyterhub for azure labs
- show and tell: a) jupyter doing an assessment, get it right, get it wrong, display the configureation file to see what it looks like; b) same using vscode; c) submit assignment .... remark about inhouse code, todo inegrate with blackboard;

Does & don't:

Does: be very specific, provide as much of the framework as you dare (API's, names); stress capitalisation; floating point comparisons and use of norms; tests your tests (setting up CI); need to break assessments into multiple steps...enables giving specific feedback on what has gone wrong;

Don't: don't use plots/figures as basis of tests; 


Presentation style - one person speaking and one person moderating.
