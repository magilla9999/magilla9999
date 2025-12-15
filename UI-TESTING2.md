# ✅ RailScanPro Homepage QA Checklist

This checklist is designed for testers of all experience levels. Use the "Pass/Fail" and "Notes" columns to track your results.

| Section | Test Case | Action | Expected Result | Pass/Fail | Notes |
|--------|-----------|--------|------------------|-----------|-------|
| Cookie Consent | Accept All | Click | Popup disappears and saves choice | Pass |  Assume it saves the choice |
| Cookie Consent | Essential Only | Click | Popup disappears and saves choice | Pass |  Assume it saves the choice |
| Cookie Consent | Decline | Click | Popup disappears and opens "Cookie Settings" button | Pass | Cookie settings button opens Cookie Consent |
| Cookie Consent | Manage Preferences | Click | Opens cookie settings modal | NA | There is no manage preferences |
| Cookie Consent | Open Requested Document | Click | Opens cookie policy document | Fail | ERROR: Legal document not found: cookie-policy.md (searched at: /app/docs/legal/cookie-policy.md) |
| Cookie Consent | Open Requested Document | Click | Opens privacy policy document | Fail | ERROR: Legal document not found: privacy-policy.md (searched at: /app/docs/legal/privacy-policy.md) |
| Navigation | Features | Click | Scrolls or navigates to Features section | Pass |  Scrolls to section "Everything You Need in One Depot" |
| Navigation | Pricing | Click | Displays pricing details | Pass | Scrolls to section "Choose Your Plan" |
| Navigation | Contact | Click | Opens contact section or form | Fail | Nothing happens when I click it |
| Navigation | Sign In | Click | Opens login modal or page |  |  |
| Navigation | Get Started | Click | Begins registration process | Pass | Opens create login page. The verification email mentions a button but I did not see one, but was able to click the URL in the helpful tips: section |
|Registration Email Link | Opens home page for user | Click | | | |
| Navigation | Sign Out | Click | I would expect it to open Home Page again |  Fail | It opens a page with what looks like possible json: \{"message":"Signed out"\} |
| CTA Buttons | Join the Waitlist | Click | Opens waitlist form or redirects |  |  |
| CTA Buttons | Try A Vision Demo | Click | Launches demo or redirects |  |  |
| Features | Snap & Photos | Scroll | Section is visible and aligned |  |  |
| Features | AI Does the Rest | Scroll | Section is visible and aligned |  |  |
| Features | Review & Save | Scroll | Section is visible and aligned |  |  |
| Visual | Hover Effects | Hover over buttons | Visual change (color, shadow, etc.) |  |  |
| Visual | Image Load | View all images | All images load correctly |  |  |
| Mobile | Resize Browser | Resize window or use mobile view | Layout adjusts properly |  |  |
| Mobile | Tap Buttons | Tap on mobile | Buttons are responsive and easy to tap |  |  |
| Accessibility | Tab Navigation | Use Tab key | Focus moves logically through buttons |  |  |
| Accessibility | Enter Key | Press Enter on focused button | Triggers correct action |  |  |
| Accessibility | Button Labels | Inspect buttons | Labels are clear and descriptive |  |  |
| General | Broken Links | Click all links | No 404 or broken links |  |  |
| General | Button Response | Click all buttons | All respond appropriately |  |  |
| General | Spelling & Grammar | Review text | No typos or grammar issues |  |  |

---

## 🛠️ Tips for QA Team
- Use **Chrome DevTools** to simulate mobile devices.
- Use **Incognito Mode** to test cookie behavior.
- Take screenshots of any bugs or unexpected behavior.
- If unsure, ask: “What should happen when I click this?”
