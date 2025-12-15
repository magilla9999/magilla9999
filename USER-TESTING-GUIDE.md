# RailScanPro User Testing Guide

**Version:** 1.0
**Date:** December 2025
**Environment:** https://railscanpro.com

Welcome to RailScanPro testing! This guide will help you explore and test the platform's features. Please report any bugs, confusing UI, or suggestions as you go.

Testing should be done via UI links and not using full paths, e.g. /auth/register
---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Feature Testing Areas](#feature-testing-areas)
   - [Authentication & Account](#1-authentication--account)
   - [Asset Management](#2-asset-management-inventory)
   - [Photos & Media](#3-photos--media)
   - [Locations](#4-locations-storage)
   - [Social Features (Telegraph)](#5-social-features-telegraph)
   - [Marketplace](#6-marketplace)
   - [Wishlist](#7-wishlist)
   - [Operations & Gaming](#8-operations--gaming)
   - [Settings & Profile](#9-settings--profile)
   - [Subscription & Billing](#10-subscription--billing)
3. [Mobile Testing](#mobile-testing)
4. [Terminal Mode (Retro UI)](#terminal-mode-retro-ui)
5. [Bug Reporting Template](#bug-reporting-template)

---

## Getting Started
This section tests initial connection to https://railscanpro.com before account creation or login.

| Section | Test Case | Action | Expected Result | Pass/Fail | Notes |
|--------|-----------|--------|------------------|-----------|-------|
| Cookie Consent | Accept All | Click | Popup disappears and saves choice | Pass |  Assume it saves the choice |
| Cookie Consent | Essential Only | Click | Popup disappears and saves choice | Pass |  Assume it saves the choice |
| Cookie Consent | Decline | Click | consent disappears and blue "Cookie Settings" button pops up | Pass | Cookie settings button opens Cookie Consent |
| Cookie Consent | Manage Preferences | Click | Opens cookie settings modal | NA | There is no manage preferences |
| Cookie Consent | Open Requested Document | Click | Opens cookie policy document | Pass | Opens Cookie Policy Last updated: November 26, 2025 and Back to home returns back to initial page|
| Cookie Consent | Open Requested Document | Click | Opens privacy policy document | Pass | Opens Privacy Policy Last updated: November 26, 2025 and Back to home returns back to initial page|

### Navigation Overview

- **Top Bar**: RailScanPro(Home), Features, Pricing, About, Blog, Sign in, Claim Founder Spot
 
| Section | Test Case | Action | Expected Result | Pass/Fail | Notes |
|--------|-----------|--------|------------------|-----------|-------|
| RailScanPro(Home)| Top Bar | Click | Navigate back to main home page | Pass | Notes |
| Features | Top Bar | Click | Navigate to feature page |  Pass | It navigates to the Three Reasons to Join RailScanPro section in main page|
| Pricing | Top Bar | Click | Navigate to pricing page | Pass | It navigates to a page titled Choose Your Plan which looks similar but not the same as the Lock in Founding Prices. It should be consistent with the Lock in page (i think anyway). It also has a different Top Bar that is hard to read.  |
| About | Top Bar | Click | Navigate to about page | Pass | It navigates to an about page that is very hard to read because the page is white and the text is greyed out. Also it has a different top bar |
| Blog | Top Bar | Click | Navigate to blog page | Pass | This page seems fine, nothing in it yet except there is a subscribe |
| Subscribe | Blog | Add email and click subscribe | Successful message and a Welcome email sent | Semi-Pass | It sends an email, but the unsubscribe link is wrong. The mail includes the following \<small\>Don't want these emails? \<a href='https://www.railscanpro.com/unsubscribe/4w8CTzILdUG6Osgo9NEjvA' style='color: #60a5fa;'>Unsubscribe</a></small>. The explore the blog link works|
| Sign In| Top Bar | Click | Navigate to Sign in to RailScanPro | Pass | Does include greyed out Google / Apple / Facebook (assuming these will be enabled at some point) . Be nice if there was a show readable password |
| Forgot password | Sign In | Click | Navigate to Reset your password page| Pass | Notes |
| Send Reset Link | Forgot password | Click | Navigate to Reset your password page| Pass | Password Reset Request received |
| Password Reset Request | Forgot password | Click | Password reset link navigates to Reset your password page | Fail | get error Password reset failed. The link may be invalid or expired.|
| Password Reset Request | Forgot password | Click | Password reset link navigates to Reset your password page | Pass (iphone) | get error Password reset failed. The link may be invalid or expired.|
| create a new account | Sign in | Click | create a new account link navigates to Create your account page | Pass | Notes |
| Create your account |create a new account | Sign in | Click | create a new account link navigates to Create your account page | Pass | Noters|
| Claim Founder Spot| Top Bar | Click | Navigate to claim found spot pagee | Pass/Fail | It navigates to Lock In Founding Prices Now section in main page |
| Personal | Lock in Found Prices Now(toggles)| Toggle | Displays Personal Plan pricing| Pass/Fail | Notes |
| Personal | Monthly/Annual | Toggle | Displays Monthly or Annual Pricing | Pass/Fail | Notes |
| Club/Museum | Lock in Found Prices Now(toggles)| Toggle | Displays Personal Plan pricing| Pass/Fail | Notes |
| Club/Museum | Monthly/Annual | Toggle | Displays Monthly or Annual Pricing | Pass/Fail | Notes |

<!--
Source - https://stackoverflow.com/a
Posted by Waylan, modified by community. See post 'Timeline' for change history
Retrieved 2025-12-15, License - CC BY-SA 4.0
-->
