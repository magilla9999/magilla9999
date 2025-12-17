## Table Of Contents
1. [Blog](#blog)
2. [Bottom Links](#bottom-links)
3. [Home Page](#home-page)
4. [Pricing Toggles](#pricing-toggles)
5. [Sign In](#sign-in)
---

## Blog
| Section | Test Case | Action | Expected Result | Pass/Fail | Notes |
|---------|-----------|--------|-----------------|-----------|-------|
| Blog | Subscribe | Add email and click subscribe | Successful message and a Welcome email sent | Semi-Pass | It sends an email, but the unsubscribe link is wrong. The explore the blog link works |
## Bottom Links
| Section | Test Case | Action | Expected Result | Pass/Fail | Notes |
|---------|-----------|--------|-----------------|-----------|-------|
| Format | Quick Links | Observation | Same as top bar order | NA | Just an observation, order is different from top bar (Features,Pricing,About,Blog). |
| Quick Links | Pricing | Click | Navigate to pricing page | Pass | It navigates to a page titled Choose Your Plan which looks similar but not the same as the Lock in Founding Prices. It should be consistent with the Lock in page (i think anyway). It also has a different Top Bar that is hard to read. |
| Quick Links | Features | Click | Navigate to feature page | Pass | It navigates to the Three Reasons to Join RailScanPro section in main page |
| Quick Links | About Us | Click | Navigate to about page | Pass | It navigates to an about page that is very hard to read because the page is white and the text is greyed out. Also it has a different top bar. Not consistent with top bar |
| Quick Links | Blog | Click | Navigate to blog page | Pass | This page seems fine, nothing in it yet except there is a subscribe |
| Legal | All Legal Documents | Click | Navigate to list of legal documents | Pass | Opens Legal page with links to all legal documents. Clicking on each open correct page. Noticed it has a different Bottom bar then main page |
| Legal | Privacy Policy | Click | Navigate to privacy policy | Pass | Opens Privacy Policy Last updated: November 26, 2025 and Back to home returns back to initial page |
| Legal | Terms of Service | Click | Navigate to Terms of service | Pass | Opens Terms of Service Last updated: November 26, 2025 and Back to home returns back to initial page |
| Legal | Cookie Policy | Click | Navigate to cookie policy | Pass | Opens Cookie Policy Last updated: November 26, 2025 and Back to home returns back to initial page |
## Home Page
| Section | Test Case | Action | Expected Result | Pass/Fail | Notes |
|---------|-----------|--------|-----------------|-----------|-------|
| Cookie Consent | Accept All | Click | Popup disappears and saves choice | Pass | Assume it saves the choice |
| Cookie Consent | Essential Only | Click | Popup disappears and saves choice | Pass | Assume it saves the choice |
| Cookie Consent | Decline | Click | consent disappears and blue "Cookie Settings" button pops up | Pass | Cookie settings button opens Cookie Consent |
| Cookie Consent | Manage Preferences | Click | Opens cookie settings modal | NA | There is no manage preferences |
| Cookie Consent | Open Requested Document | Click | Opens cookie policy document | Pass | Opens Cookie Policy Last updated: November 26, 2025 and Back to home returns back to initial page |
| Cookie Consent | Open Requested Document | Click | Opens privacy policy document | Pass | Opens Privacy Policy Last updated: November 26, 2025 and Back to home returns back to initial page |
| Top Bar | RailScanPro(Home) | Click | Navigate back to main home page | Pass |  |
| Top Bar | Features | Click | Navigate to feature page | Pass | It navigates to the Three Reasons to Join RailScanPro section in main page |
| Top Bar | Pricing | Click | Navigate to pricing page | Pass | It navigates to a page titled Choose Your Plan which looks similar but not the same as the Lock in Founding Prices. It should be consistent with the Lock in page (i think anyway). It also has a different Top Bar that is hard to read. |
| Top Bar | About | Click | Navigate to about page | Pass | It navigates to an about page that is very hard to read because the page is white and the text is greyed out. Also it has a different top bar |
| Top Bar | Blog | Click | Navigate to blog page | Pass | This page seems fine, nothing in it yet except there is a subscribe |
| Top Bar | Claim Founder Spot | Click | Navigate to Lock In Founding Prices Now section in main page | Pass |  |
| Top Bar | Sign In | Click | Navigate to Sign in to RailScanPro | Pass | Does include greyed out Google / Apple / Facebook (assuming these will be enabled at some point). Be nice if there was a show readable password |
## Pricing Toggles
| Section | Test Case | Action | Expected Result | Pass/Fail | Notes |
|---------|-----------|--------|-----------------|-----------|-------|
| Lock in Founding Prices Now(toggles) | Personal | Toggle | Displays Collector, Family, Pro pricing | Pass |  |
| Monthly/Annual | Personal | Toggle | Displays Monthly or Annual Pricing | Pass | Switches between Monthly or Annual pricing for Collector, Family, Pro |
| Personal (Get Started) | Collector,Family,Pro | Click | navigates to payment page for collector,family,pro | Pass | If Monthly or Annual is set the correct price is shown. If I click back it goes back to main page and personal is still set. If a family has more than 5 people that want to join would they have to use Pro? |
| Lock in Founding Prices Now(toggles) | Club/Museum | Toggle | Displays Club/Museum Plan pricing | Pass |  |
| Monthly/Annual | Club/Museum | Toggle | Displays Monthly or Annual Pricing | Pass |  |
| Club/Museum (Get Started) | Club,Museum | Click | navigates to payment page for club,museum | Semi-Pass | If monthly or Annual is set the correct price is shown. If I click back it goes back to main page and personal is set instead of Club/museum |
| Main page | View Pricing Plans Above | Click | Navigate to pricing section on home page | Pass |  |
## Sign In
| Section | Test Case | Action | Expected Result | Pass/Fail | Notes |
|---------|-----------|--------|-----------------|-----------|-------|
| Sign In | Forgot password | Click | Navigate to Reset your password page | Pass |  |
| Forgot password | Send Reset Link | Click | Navigate to Reset your password page | Pass | Password Reset Request received |
| Forgot password | Password Reset Request | Click | Password reset link navigates to Reset your password page | Fail | get error Password reset failed. The link may be invalid or expired. |
| Forgot password | Password Reset Request | Click | Password reset link navigates to Reset your password page | Pass (iphone) |  |
| Sign in | create a new account | Click | create a new account link navigates to Create your account page | Pass |  |
| create a new account | Create your account | Click | create a new account link navigates to Create your account page | Pass |  |
