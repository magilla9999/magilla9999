# RailScanPro User Testing Guide

**Version:** 1.0
**Date:** December 2025
**Environment:** https://localhost:7228 (Development)

Welcome to RailScanPro testing! This guide will help you explore and test the platform's features. Please report any bugs, confusing UI, or suggestions as you go.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Quick Test Checklist](#quick-test-checklist)
3. [Feature Testing Areas](#feature-testing-areas)
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
4. [Mobile Testing](#mobile-testing)
5. [Terminal Mode (Retro UI)](#terminal-mode-retro-ui)
6. [Bug Reporting Template](#bug-reporting-template)

---

## Getting Started

### Test Account Setup

1. Navigate to https://localhost:7228 or try https://railscanpro.com
2. Click "Get Started" or go to `/auth/register`
3. Create a new account with:
   - Valid email (you'll need to verify)
   - Password (minimum 8 characters)
   - Display name

### Navigation Overview

- **Left Sidebar**: Main navigation (desktop)
- **Bottom Tabs**: Mobile navigation (5 main areas)
- **Hamburger Menu**: Full menu access on mobile
- **Top Bar**: Search, notifications, profile

---

## Quick Test Checklist

Use this for a 15-minute smoke test:

- [ ] Can register a new account
- [ ] Can log in/log out
- [ ] Dashboard loads without errors
- [ ] Can add a new asset (any method)
- [ ] Can upload a photo
- [ ] Can view asset list
- [ ] Can access Telegraph (social feed)
- [ ] Can access Marketplace
- [ ] Navigation works on mobile
- [ ] Settings page loads

---

## Feature Testing Areas

### 1. Authentication & Account

| Test | URL | What to Check |
|------|-----|---------------|
| Register | `/auth/register` | Form validation, email verification flow |
| Login | `/auth/login` | Correct credentials work, error for wrong password |
| Forgot Password | `/auth/forgot-password` | Email sends, reset link works |
| Logout | Click profile > Logout | Redirects to landing page |

**Test Scenarios:**
- [ ] Register with valid email
- [ ] Try registering with same email twice (should fail)
- [ ] Login with correct credentials
- [ ] Login with wrong password (should show error)
- [ ] Use "Forgot Password" flow
- [ ] Log out and verify session ends

---

### 2. Asset Management (Inventory)

**Main URL:** `/app/asset-management`

This is the core feature - tracking model railroad equipment.

#### Adding Assets

| Method | URL | Description |
|--------|-----|-------------|
| Quick Add | `/app/asset-management/add/quick` | Fast entry with minimal fields |
| Form First | `/app/asset-management/add/form-first` | Detailed form entry |
| Photo First | `/app/asset-management/add/photo-first` | Start with photo, AI extracts data |
| Box/Receipt | `/app/asset-management/add/box-receipt` | Scan product box or receipt |
| Barcode | `/app/asset-management/add/barcode` | Scan UPC/EAN barcode |
| Import | `/app/asset-management/import` | CSV/JSON bulk import |

**Test Scenarios:**
- [ ] Add asset using Quick Add
- [ ] Add asset using Photo First (test AI recognition)
- [ ] Edit an existing asset
- [ ] Delete an asset
- [ ] Search/filter asset list
- [ ] Sort assets by different columns
- [ ] View asset detail page
- [ ] Generate QR code for asset (`/app/asset-management/qr/{Id}`)

#### Asset List Views

| View | URL | Description |
|------|-----|-------------|
| Dashboard | `/app/asset-management` | Overview with stats |
| List View | `/app/asset-management/list` | Grid/table view |
| Multi-View | `/app/asset-management/list-multi-view` | Card/grid/list toggle |

**Test Scenarios:**
- [ ] Switch between view modes
- [ ] Use filters (type, manufacturer, condition)
- [ ] Test pagination with many items
- [ ] Export asset list

---

### 3. Photos & Media

**Main URL:** `/app/photos`

| Feature | URL | What to Test |
|---------|-----|--------------|
| Photo Library | `/app/photos` | View all photos across assets |
| Upload | `/app/photos/upload` | Upload new photos |
| AI Analysis | `/app/photos/analyze` | AI identifies items in photos |
| Organize | `/app/photos/organize` | Bulk photo organization |

**Test Scenarios:**
- [ ] Upload single photo
- [ ] Upload multiple photos at once
- [ ] View photo in lightbox
- [ ] Delete a photo
- [ ] Use AI analysis on a locomotive photo
- [ ] Associate photo with specific asset

---

### 4. Locations (Storage)

**Main URL:** `/app/locations`

Track where your equipment is stored.

| Feature | URL | What to Test |
|---------|-----|--------------|
| Location List | `/app/locations` | View all storage locations |
| Create Location | `/app/locations/create` | Add new location |
| Location Detail | `/app/locations/detail/{Id}` | View items at location |
| Map View | `/app/locations/map` | Visual location map |

**Test Scenarios:**
- [ ] Create a new location (e.g., "Display Case A")
- [ ] Assign an asset to a location
- [ ] Move asset between locations
- [ ] View location capacity
- [ ] Delete empty location

---

### 5. Social Features (Telegraph)

**Main URL:** `/app/telegraph`

The social hub using railroad telegraph terminology.

#### Telegraph Terminology Guide

| Term | Meaning |
|------|---------|
| Main Line | Public feed (all posts) |
| Connections | People you follow |
| Lines | Groups/communities |
| Circuits | Discussion forums |
| Private Wire | Direct messages |
| Wire | A post/message |

#### Features to Test

| Feature | URL | What to Test |
|---------|-----|--------------|
| Telegraph Office | `/app/telegraph` | Main social feed |
| Main Line | `/app/social/main-line` | Public posts |
| Connections | `/app/social/connections` | Follow/unfollow users |
| Lines (Groups) | `/app/social/lines` | Join/leave groups |
| Circuits (Forums) | `/app/social/circuits` | Forum discussions |
| Private Wire (DMs) | `/app/private-wire` | Direct messaging |
| My Wires | `/app/social/my-wires` | Your posts |

**Test Scenarios:**
- [ ] Create a new post (Wire)
- [ ] Like/unlike a post
- [ ] Comment on a post
- [ ] Follow another user
- [ ] View someone's profile
- [ ] Create a new Line (group)
- [ ] Post in a Circuit (forum)
- [ ] Send a Private Wire (DM)
- [ ] View notification when someone interacts with your post

---

### 6. Marketplace

**Main URL:** `/app/marketplace`

Buy, sell, and auction model railroad equipment.

| Feature | URL | What to Test |
|---------|-----|--------------|
| Browse Listings | `/app/marketplace` | View all listings |
| Create Listing | `/app/marketplace/create` | List item for sale |
| Create Auction | `/app/marketplace/create-auction` | Start an auction |
| My Listings | `/app/marketplace/my-listings` | Manage your listings |
| Purchases | `/app/marketplace/purchases` | Purchase history |
| Sales | `/app/marketplace/sales` | Sales history |

**Test Scenarios:**
- [ ] Browse marketplace listings
- [ ] Create a fixed-price listing
- [ ] Create an auction listing
- [ ] Edit a listing
- [ ] End/cancel a listing
- [ ] Save a search
- [ ] Filter by category/price/condition

---

### 7. Wishlist

**Main URL:** `/app/wishlist`

Track items you want to acquire.

| Feature | URL | What to Test |
|---------|-----|--------------|
| My Wishlist | `/app/wishlist` | View wishlist items |
| Add Item | `/app/wishlist/create` | Add new wishlist item |
| Share Wishlist | `/app/wishlist/shared` | Share with others |
| Recommendations | `/app/wishlist/recommendations` | AI suggestions |

**Test Scenarios:**
- [ ] Add item to wishlist manually
- [ ] Set priority level
- [ ] Add from marketplace listing
- [ ] Share wishlist publicly
- [ ] Mark item as acquired
- [ ] Delete wishlist item

---

### 8. Operations & Gaming

**Main URL:** `/app/operations`

Model railroad operations simulation.

| Feature | URL | What to Test |
|---------|-----|--------------|
| Operations Hub | `/app/operations` | Main dashboard |
| Daily Operations | `/app/operations/daily` | Today's session |
| Layouts | `/app/operations/layouts` | Track plans |
| Trains | `/app/operations/trains` | Operating consists |
| Practice Puzzles | `/app/operations/practice` | Switching puzzles |
| Achievements | `/app/operations/achievements` | Earned badges |
| Leaderboard | `/app/operations/leaderboard` | Rankings |

**Test Scenarios:**
- [ ] Create a new layout
- [ ] Add rolling stock to a train consist
- [ ] Start a practice puzzle
- [ ] Complete a puzzle and check score
- [ ] View achievements

---

### 9. Settings & Profile

**Main URL:** `/app/settings`

| Section | URL | What to Configure |
|---------|-----|-------------------|
| Profile | `/app/profile` | Display name, avatar, bio |
| Railroad | `/app/settings/railroad` | Railroad name, era, scale |
| Notifications | `/app/settings/notifications` | Email/push preferences |
| Privacy | `/app/settings/privacy` | Profile visibility |
| Theme | `/app/settings/theme` | Light/dark/terminal mode |
| Team | `/app/team` | Organization members |

**Test Scenarios:**
- [ ] Update profile photo
- [ ] Change display name
- [ ] Configure railroad profile
- [ ] Toggle notification settings
- [ ] Change theme (light/dark)
- [ ] Invite team member

---

### 10. Subscription & Billing

**Main URL:** `/app/subscription`

| Feature | URL | What to Test |
|---------|-----|--------------|
| Subscription Status | `/app/subscription` | Current plan |
| Billing | `/app/subscription/billing` | Payment info |
| Usage | `/app/subscription/usage` | Feature usage |
| Upgrade | `/app/subscription/upgrade` | Plan comparison |

**Test Scenarios:**
- [ ] View current plan details
- [ ] Check feature usage (items, photos, etc.)
- [ ] View billing history
- [ ] Attempt upgrade flow (test mode)

---

## Mobile Testing

Test on phone or use browser dev tools (F12 > Toggle Device).

### Mobile Bottom Navigation

The mobile bottom bar has 5 tabs:
1. **Telegraph** - Social feed
2. **Assets** - Asset management
3. **Scan** - QR/barcode scanner
4. **Market** - Marketplace
5. **More** - Everything else

**Test Scenarios:**
- [ ] All 5 bottom tabs work
- [ ] Hamburger menu opens full navigation
- [ ] Asset list is scrollable
- [ ] Photo upload works from camera
- [ ] Forms are usable on small screen
- [ ] Keyboard doesn't cover input fields

---

## Terminal Mode (Retro UI)

Experience the retro IBM 3270 mainframe aesthetic!

**Enable:** Settings > Theme > Terminal Mode

Or visit terminal URLs directly:
- `/app/terminal/social/telegraph`
- `/app/terminal/social/circuits`
- `/app/terminal/social/connections`

**Test Scenarios:**
- [ ] Terminal mode renders correctly
- [ ] Phosphor color options work (green/amber/white)
- [ ] Can switch back to modern mode
- [ ] All terminal pages are functional

---

## Bug Reporting Template

When you find an issue, please report it with:

```
### Bug Title
[Short description]

### Steps to Reproduce
1. Go to [URL]
2. Click [button/link]
3. Enter [data]
4. [What happened]

### Expected Behavior
[What should have happened]

### Actual Behavior
[What actually happened]

### Screenshots
[Attach if helpful]

### Environment
- Browser: [Chrome/Firefox/Safari/Edge]
- Device: [Desktop/Mobile]
- Screen Size: [if relevant]
- User Type: [New user/Existing user]
```

---

## Feature Request Template

Have an idea? We'd love to hear it!

```
### Feature Title
[Short description]

### Problem It Solves
[What pain point does this address?]

### Proposed Solution
[How would it work?]

### Alternatives Considered
[Other ways to solve this?]

### Priority
[Nice to have / Important / Critical]
```

---

## Thank You!

Your testing helps make RailScanPro better for the model railroad community. Please report all issues, no matter how small - typos, confusing labels, slow pages, and broken features are all valuable feedback.

**Questions?** Contact the development team or submit feedback at `/app/feedback/report-bug`

Happy testing! 🚂
