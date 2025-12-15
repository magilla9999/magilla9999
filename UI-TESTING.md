# RailScanPro Comprehensive UI Test Cases

## 1. Navigation & Links
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| NAV-001 | Verify top navigation links | Click Features, Pricing, About, Blog, Sign In | Each link redirects correctly |
| NAV-002 | Verify footer links | Click Privacy Policy, Terms, Cookie Policy | Each opens correct page |
| NAV-003 | Verify external links | Click Stripe/Azure references | Redirects to external sites in new tab |
| NAV-004 | Verify logo click | Click RailScanPro logo | Redirects to homepage |

---

## 2. Homepage UI
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| HOME-001 | Hero banner responsiveness | Resize window (desktop, tablet, mobile) | Banner scales correctly |
| HOME-002 | CTA button functionality | Click “Get Started” | Redirects to signup/pricing |
| HOME-003 | Text readability | Check font size, contrast | Text legible on all devices |
| HOME-004 | Image loading | Verify hero images/icons | Images load without distortion |

---

## 3. Pricing Page
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| PRICE-001 | Plan card layout | View Collector, Family, Pro cards | Cards aligned, pricing visible |
| PRICE-002 | CTA buttons | Click “Subscribe” | Redirects to payment flow |
| PRICE-003 | Discount display | Check Founding Member discount | Discount visible and applied |
| PRICE-004 | Responsiveness | Resize window | Cards stack correctly on mobile |

---

## 4. Features Page
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| FEAT-001 | Icon alignment | Verify feature icons | Icons aligned with text |
| FEAT-002 | Section spacing | Scroll through page | Sections evenly spaced |
| FEAT-003 | Responsiveness | Resize window | Features adapt to screen size |

---

## 5. About Page
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| ABOUT-001 | Content readability | Check mission, story, team sections | Text legible and aligned |
| ABOUT-002 | Image placement | Verify team/brand images | Images load correctly |
| ABOUT-003 | Responsiveness | Resize window | Layout adapts without overlap |

---

## 6. Blog Page
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| BLOG-001 | Blog list layout | View blog entries | Titles, excerpts aligned |
| BLOG-002 | Blog navigation | Click blog entry | Redirects to full article |
| BLOG-003 | Responsiveness | Resize window | Blog cards stack correctly |

---

## 7. Sign In Page
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| LOGIN-001 | Form validation | Submit empty form | Error message displayed |
| LOGIN-002 | Invalid credentials | Enter wrong email/password | Error message displayed |
| LOGIN-003 | Valid login | Enter correct credentials | Redirects to dashboard |
| LOGIN-004 | Password masking | Enter password | Characters masked |
| LOGIN-005 | Responsiveness | Resize window | Form adapts to screen size |

---

## 8. Cookie Banner
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| COOKIE-001 | Banner visibility | Load site | Banner appears |
| COOKIE-002 | Accept all | Click “Accept All” | Preferences saved, banner dismissed |
| COOKIE-003 | Decline | Click “Decline” | Only essential cookies active |
| COOKIE-004 | Essential only | Click “Essential Only” | Preferences saved correctly |

---

## 9. Community UI
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| COM-001 | Feed posting | Create post with text/image | Post appears correctly |
| COM-002 | Club creation | Create new club | Club visible in directory |
| COM-003 | Messaging | Send message | Recipient receives instantly |
| COM-004 | Marketplace | List item for sale | Item visible in marketplace |

---

## 10. Gaming UI
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| GAME-001 | Daily puzzle | Access puzzle | Puzzle loads correctly |
| GAME-002 | Puzzle completion | Solve puzzle | Points awarded |
| GAME-003 | Logistics simulation | Join simulation | Role UI loads correctly |
| GAME-004 | Leaderboard | View leaderboard | Scores displayed correctly |

---

## 11. Accessibility
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| ACC-001 | Keyboard navigation | Tab through site | All elements accessible |
| ACC-002 | Screen reader labels | Use screen reader | ARIA labels descriptive |
| ACC-003 | Color contrast | Check text/background | Meets WCAG 2.1 AA |
| ACC-004 | Alt text | Inspect images | Alt text present and meaningful |

---

## 12. Responsiveness
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| RESP-001 | Desktop layout | View site at 1920x1080 | Layout correct |
| RESP-002 | Tablet layout | View site at 768x1024 | Layout adapts |
| RESP-003 | Mobile layout | View site at 375x667 | Layout stacks correctly |
| RESP-004 | Orientation change | Switch mobile portrait/landscape | Layout adapts seamlessly |

---

## 13. Error Handling
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| ERR-001 | 404 page | Enter invalid URL | Custom 404 page displayed |
| ERR-002 | Form errors | Submit invalid data | Error messages clear |
| ERR-003 | Timeout | Simulate slow connection | Loading indicators visible |

---

## 14. Visual Consistency
| Test Case ID | Description | Steps | Expected Result | Pass/Fail |
|--------------|-------------|-------|-----------------|-----------------|
| VIS-001 | Font consistency | Check across pages | Fonts consistent |
| VIS-002 | Color palette | Inspect buttons, links | Colors match brand |
| VIS-003 | Hover states | Hover over buttons/links | States visible |
| VIS-004 | Alignment | Inspect sections | Elements aligned consistently |


