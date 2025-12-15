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
| RailScanPro(Home)| Top Bar | Click | Navigate back to main home page | Pass |  |
| Features | Top Bar | Click | Navigate to feature page |  Pass | It navigates to the Three Reasons to Join RailScanPro section in main page|
| Pricing | Top Bar | Click | Navigate to pricing page | Pass | It navigates to a page titled Choose Your Plan which looks similar but not the same as the Lock in Founding Prices. It should be consistent with the Lock in page (i think anyway). It also has a different Top Bar that is hard to read.  |
| About | Top Bar | Click | Navigate to about page | Pass | It navigates to an about page that is very hard to read because the page is white and the text is greyed out. Also it has a different top bar |
| Blog | Top Bar | Click | Navigate to blog page | Pass | This page seems fine, nothing in it yet except there is a subscribe |
| Subscribe | Blog | Add email and click subscribe | Successful message and a Welcome email sent | Semi-Pass | It sends an email, but the unsubscribe link is wrong. The mail includes the following \<small\>Don't want these emails? \<a href='https://www.railscanpro.com/unsubscribe/4w8CTzILdUG6Osgo9NEjvA' style='color: #60a5fa;'>Unsubscribe</a></small>. The explore the blog link works|
| Sign In| Top Bar | Click | Navigate to Sign in to RailScanPro | Pass | Does include greyed out Google / Apple / Facebook (assuming these will be enabled at some point) . Be nice if there was a show readable password |
| Forgot password | Sign In | Click | Navigate to Reset your password page| Pass |  |
| Send Reset Link | Forgot password | Click | Navigate to Reset your password page| Pass | Password Reset Request received |
| Password Reset Request | Forgot password | Click | Password reset link navigates to Reset your password page | Fail | get error Password reset failed. The link may be invalid or expired.|
| Password Reset Request | Forgot password | Click | Password reset link navigates to Reset your password page | Pass (iphone) | |
| create a new account | Sign in | Click | create a new account link navigates to Create your account page | Pass |  |
| Create your account |create a new account | Click | create a new account link navigates to Create your account page | Pass | |
| Claim Founder Spot| Top Bar | Click | Navigate to Lock In Founding Prices Now section in main page | Pass |  |
| Personal | Lock in Founding Prices Now(toggles)| Toggle | Displays Collector, Family, Pro pricing | Pass |  |
| Personal | Monthly/Annual | Toggle | Displays Monthly or Annual Pricing | Pass | Switches between Monthly or Annual pricing for Collector, Family, Pro |
| Collector,Family,Pro | Personal (Get Started) | Click | navigates to payment page for collector,family,pro | Pass | If Monthly or Annual is set the correct price is shown. If I click back it goes back to main page and personal is still set. If a family has more than 5 people that want to join would they have to use Pro?|
| Club/Museum | Lock in Founding Prices Now(toggles)| Toggle | Displays Club/Museum Plan pricing| Pass |   |
| Club/Museum | Monthly/Annual | Toggle | Displays Monthly or Annual Pricing | Pass |  |
| Club,Museum | Club/Museum (Get Started) | Click | navigates to payment page for club,museum | Semi-Pass | If monthly or Annual is set the correct price is shown. If I click back it goes back to main page and personal is set instead of Club/museum|
| View Pricing Plans Above | Main page | Click | Navigate to pricing page | Pass | |

- ** Bottom Links **: Quick Links, Legal, Trust&Security

| Section | Test Case | Action | Expected Result | Pass/Fail | Notes |
|--------|-----------|--------|------------------|-----------|-------|
| Quick Links | Format | Observation | Same as top bar order | NA | Just an observation, order is different from top bar (Features,Pricing,About,Blog).|
| Pricing | Quick Links | Click | Navigate to pricing page | Pass | It navigates to a page titled Choose Your Plan which looks similar but not the same as the Lock in Founding Prices. It should be consistent with the Lock in page (i think anyway). It also has a different Top Bar that is hard to read.  |
| Features | Quick Links | Click | Navigate to feature page |  Pass | It navigates to the Three Reasons to Join RailScanPro section in main page|
| About Us | Quick Links | Click | Navigate to about page | Pass | It navigates to an about page that is very hard to read because the page is white and the text is greyed out. Also it has a different top bar . not consistent with top bar |
| Blog | Quick Links | Click | Navigate to blog page | Pass | This page seems fine, nothing in it yet except there is a subscribe |
| All Legal Documents | Legal | Click | Navigate to list of legal documents | Pass | Opens Legal page with links to all legal documents. Clicking on each open correct page. Noticed it has a different Bottom bar then main page|
| Privacy Policy |  Legal | Click | Navigate to privacy policy | Pass | Opens Privacy Policy Last updated: November 26, 2025 and Back to home returns back to initial page|
| Terms of Service |  Legal | Click | Navigate to Terms of service | Pass | Opens Terms of Service Last updated: November 26, 2025 and Back to home returns back to initial page|
| Cookie Policy |  Legal | Click | Navigate to cookie policy | Pass | Opens Cookie Policy Last updated: November 26, 2025 and Back to home returns back to initial page|
