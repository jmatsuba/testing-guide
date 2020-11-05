# Rails Testing Guide

This is Animikii's Rails Testing Guide.

## Table of Contents
  1. [Introduction](#introduction)

  1. [Resources](#resources)
      1. [Example Projects Tests](#example-projects-tests)
      1. [Other](#other)


## Introduction
This guide is a early draft based on feedback given by our engineering staff as of November 2020.

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

Part of this strategy includes encapsulating a rail app's business logic in some sort of service object to make testing easier.

## Tools
`minitest` over `rspec`. Minitest is the default test framework, has a smaller learning curve, and is faster.

`fixtures` or `factories` for test data. There is no hard rule on this one. Fixtures are Rails’ default way to prepare and reuse test data. However, opinions on which to use in the industry are mixed. AKII has used both in past projects.

https://semaphoreci.com/community/tutorials/working-effectively-with-data-factories-using-factorygirl

## What We Test
### Business Logic
Business Logic should generally always be tested. Ideally located in service objects, however, if such logic lives elsewhere is should be tested. The definition of business logic is "part of the program that encodes the real-world business rules that determine how data can be created, stored, and changed".

### Scopes
Simple scopes do not need to be tested. However, if a scope's complexity starts to get confusing we should test it.

### Access Control
Access control points should be tested.

### Critical User Workflows
While feature tests are typically slow. Good practice would be to write a couple feature tests to test the most critical user workflows. Such as 

## Resources

### Example Projects Tests

https://github.com/animikii/phsa-sanyas-upgrade/tree/master/test
https://github.com/animikii/yikesite-web/tree/master/test
https://github.com/animikii/niiwin-mvp/tree/master/test
https://github.com/animikii/ahslovit-web/tree/master/test


### Other
https://guides.rubyonrails.org/testing.html
https://github.com/seattlerb/minitest
https://thoughtbot.com/blog/how-we-test-rails-applications
https://www.youtube.com/watch?v=URSWYvyc42M
https://www.youtube.com/watch?v=l-ZNxvFo4lw
