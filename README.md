# Rails Testing Guide

This is Animikii's Rails Testing Guide.

## Table of Contents
  1. [Introduction](#introduction)
      1. [What Kind of Projects We Test](#what-kind-of-projects-we-test)
      1. [What Kind of Projects We Don't Test](#what-kind-of-projects-we-dont-test)
      1. [Strategy](#strategy)

  1. [Tools](#tools)
  1. [What We Test](#what-we-test)
      1. [Business Logic](#business-logic)
      1. [Scopes](#scopes)
      1. [Access Control](#access-control)
      1. [Critical User Workflows](#critical-user-workflows)


## Introduction
This guide is an early draft based on feedback given by our engineering staff as of November 2020.

<!-- This need to be confirmed by leadership / engineering leadership -->
### What Kind of Projects We Test
- Internal applications (eg: Niiwin, Yikesite)
- Client custom software projects we intend on maintaining (eg: San'yas, AHS)
- Client custom software projects that have including automated testing in their roadmapping document or that the project

<!-- This need to be confirmed by leadership / engineering leadership -->
### What Kind of Projects We Don't Test
- Website projects hosted by Yikesite

### Strategy
The high level strategy is to test the complicated logic and to not test standard rails implementation. Judgement should be used by the application maintainers as to what they see as important to test.

Part of this strategy includes encapsulating a application's business logic in some sort of service object to make testing easier.

## Tools
`minitest` over `rspec`. Minitest is the default test framework, has a smaller learning curve, and is faster.

`fixtures` or `factories` for test data. There is no hard rule on this one. Fixtures are Rails’ default way to prepare and reuse test data. However, opinions on which to use in the industry are mixed. AKII has used both in past projects.

`selenium` for browser automation.
`cypress` (maybe) for automated browser testing.

### Resources
[Working Effectively with Factories](https://semaphoreci.com/community/tutorials/working-effectively-with-data-factories-using-factorygirl)  


## What We Test
### Business Logic
Business Logic should generally always be tested. Ideally located in service objects, however, if such logic lives elsewhere it should still be tested. The definition of business logic is "part of the program that encodes the real-world business rules that determine how data can be created, stored, and changed".

### Scopes
Simple scopes do not need to be tested. However, if a scope's complexity starts to get confusing we should test it.

### Access Control
Access control points should be tested.

### Critical User Workflows
While feature tests are typically slow. Good practice would be to write a couple feature tests to test the most critical user workflows. Such as user signup or one or two of the main features of the application.

## General Resources

### Example of Testing in our existing Projects
[San'yas Next](https://github.com/animikii/phsa-sanyas-upgrade/tree/master/test)  
[Yikesite](https://github.com/animikii/yikesite-web/tree/master/test)  
[Niiwin](https://github.com/animikii/niiwin-mvp/tree/master/test)  
[AHS Lovit](https://github.com/animikii/ahslovit-web/tree/master/test)  


### Other
[Rails Testing Documentation](https://guides.rubyonrails.org/testing.html) Official testing guide from the rails core team. Good documentation of minitest and rails specific test methods.  
[How We Test Rails Applications](https://thoughtbot.com/blog/how-we-test-rails-applications) By thoughtbot. While they use a different stack for testing the article contains some good information on how to test.   
[The Magic Tricks of Testing](https://www.youtube.com/watch?v=URSWYvyc42M) A YouTube video from Sandi Metz on what to test, and how to make refactoring less painful.  
[Minitest 6: test feistier! by Ryan Davis](https://www.youtube.com/watch?v=l-ZNxvFo4lw) A video on the background and advantages of MiniTest by the founder of Minitest.



