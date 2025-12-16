# RailScanPro User Testing Guide

**Version:** 1.1
**Date:** December 2025
**Environment:** https://localhost:7228 (Development)

Welcome to RailScanPro testing! This guide will help you explore and test the platform's features. Please report any bugs, confusing UI, or suggestions as you go.

---

## Table of Contents

1. [Getting Started](#getting-started)
2. [Quick Test Checklist](#quick-test-checklist)
3. [Feature Testing Areas](#feature-testing-areas)
   - [Authentication & Account](#1-authentication--account)
   - [Asset Management](#2-asset-management)
   - [Photos & Media](#3-photos--media)
   - [Locations](#4-locations-storage)
   - [Kits & Groupings](#5-kits--groupings)
   - [Rapid Cataloging](#6-rapid-cataloging)
   - [Bad Orders (Maintenance Issues)](#7-bad-orders-maintenance-issues)
   - [Social Features (Telegraph)](#8-social-features-telegraph)
   - [Marketplace](#9-marketplace)
   - [Wishlist](#10-wishlist)
   - [Operations & Gaming](#11-operations--gaming)
   - [Settings & Profile](#12-settings--profile)
   - [Subscription & Billing](#13-subscription--billing)
4. [Mobile Testing](#mobile-testing)
5. [Terminal Mode (Retro UI)](#terminal-mode-retro-ui)
6. [System Alerts & Banners](#system-alerts--banners)
7. [Admin Panel (Admin Users Only)](#admin-panel-admin-users-only)
8. [Bug Reporting Template](#bug-reporting-template)

---

## Getting Started

### Test Account Setup

1. Navigate to https://localhost:7228
2. Click "Get Started" or go to `/auth/register`
3. Create a new account with:
   - Valid email (you'll need to verify)
   - Password (minimum 8 characters)
   - Display name

### Navigation Overview

**Desktop:**
- **Left Sidebar**: Main navigation with sections:
  - Telegraph Office (social hub)
  - Workspace (customizable dashboard)
  - Asset Management, Photos, Documents, Maintenance, Wishlist
  - Operations (model railroad sessions)
  - Marketplace & Valuations
  - Clubs & Museums
  - AI Assistant & Reports
  - Profile, Settings, Subscription

**Mobile:**
- **Bottom Tabs**: 5 main areas (Telegraph, Assets, Scan, Market, More)
- **Hamburger Menu**: Full menu access
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
- [ ] System alerts display at top of page (if any are active)

---

## Feature Testing Areas

### 1. Authentication & Account

| Test | URL | What to Check |
|------|-----|---------------|
| Register | `/auth/register` | Form validation, email verification flow |
| Login | `/auth/login` | Correct credentials work, error for wrong password |
| Forgot Password | `/auth/forgot-password` | Email sends, reset link works |
| Logout | Click profile > Logout | Redirects to landing page |
| Welcome | `/auth/welcome` | Post-registration welcome screen |

**Test Scenarios:**
- [ ] Register with valid email
- [ ] Try registering with same email twice (should fail)
- [ ] Login with correct credentials
- [ ] Login with wrong password (should show error)
- [ ] Use "Forgot Password" flow
- [ ] Log out and verify session ends

---

### 2. Asset Management

**Main URL:** `/app/asset-management`

This is the core feature - tracking model railroad equipment.

#### Adding Assets

| Method | URL | Description |
|--------|-----|-------------|
| Add Wizard | `/app/asset-management/add` | Choose entry method |
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
- [ ] View asset detail page (`/app/asset-management/detail/{Id}`)
- [ ] Generate QR code for asset (`/app/asset-management/qr/{Id}`)
- [ ] Use QR scanner (`/app/scan`)

#### Asset List Views

| View | URL | Description |
|------|-----|-------------|
| Dashboard | `/app/asset-management` | Overview with stats |
| List View | `/app/asset-management/list` | Grid/table view |
| Multi-View | `/app/asset-management/list-multi-view` | Card/grid/list toggle |
| Categories | `/app/asset-management/categories` | Asset type management |

**Test Scenarios:**
- [ ] Switch between view modes
- [ ] Use filters (type, manufacturer, condition)
- [ ] Test pagination with many items
- [ ] Export asset list (`/app/asset-management/export`)
- [ ] Import/Export hub (`/app/asset-management/import-export`)

---

### 3. Photos & Media

**Main URL:** `/app/photos`

| Feature | URL | What to Test |
|---------|-----|--------------|
| Photo Library | `/app/photos` | View all photos across assets |
| Upload | `/app/photos/upload` | Upload new photos |
| AI Analysis | `/app/photos/analyze` | AI identifies items in photos |
| Organize | `/app/photos/organize` | Bulk photo organization |
| Edit Metadata | `/app/photos/edit-metadata` | EXIF and tag editing |
| Gallery | `/app/gallery` | Public gallery view |

**Test Scenarios:**
- [ ] Upload single photo
- [ ] Upload multiple photos at once
- [ ] View photo in lightbox
- [ ] Delete a photo
- [ ] Use AI analysis on a locomotive photo
- [ ] Associate photo with specific asset
- [ ] Photos load with proper authentication (SAS tokens)

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
| History | `/app/locations/history` | Location transaction history |

**Test Scenarios:**
- [ ] Create a new location (e.g., "Display Case A")
- [ ] Assign an asset to a location
- [ ] Move asset between locations
- [ ] View location capacity
- [ ] Delete empty location

---

### 5. Kits & Groupings

**Main URL:** `/app/kits`

Group related assets together (e.g., a consist, a train set).

| Feature | URL | What to Test |
|---------|-----|--------------|
| Kit List | `/app/kits` | View all kits |
| Create Kit | `/app/kits/new` | Create new grouping |
| Kit Detail | `/app/kits/{Id}` | View kit contents |
| Edit Kit | `/app/kits/{Id}/edit` | Modify kit |

**Test Scenarios:**
- [ ] Create a new kit
- [ ] Add multiple assets to a kit
- [ ] Remove asset from kit
- [ ] Delete a kit (assets should remain)

---

### 6. Rapid Cataloging

**Main URL:** `/app/rapid-catalog`

Bulk entry tools for cataloging large collections quickly.

| Feature | URL | What to Test |
|---------|-----|--------------|
| Rapid Catalog Hub | `/app/rapid-catalog` | Overview dashboard |
| Rapid Capture | `/app/rapid-catalog/rapid-capture` | Fast photo capture mode |
| Video Scan | `/app/rapid-catalog/video-scan` | Video-based bulk scanning |
| Batch Upload | `/app/rapid-catalog/batch-upload` | Upload many photos at once |
| Job Status | `/app/rapid-catalog/job/{JobId}` | View batch processing status |

**Test Scenarios:**
- [ ] Use rapid capture mode
- [ ] Upload batch of photos
- [ ] Check job processing status
- [ ] Review AI-processed results

---

### 7. Bad Orders (Maintenance Issues)

**Main URL:** `/app/bad-orders`

Track mechanical issues and items needing repair (railroad term for equipment out of service).

**Test Scenarios:**
- [ ] View bad order list
- [ ] Create a bad order for an asset
- [ ] Mark a bad order as resolved
- [ ] Filter by severity/status

---

### 8. Social Features (Telegraph)

**Main URL:** `/app/telegraph`

The social hub using railroad telegraph terminology.

#### Telegraph Terminology Guide

| Term | Meaning |
|------|---------|
| Telegraph Office | Main social hub |
| Main Line | Public feed (all posts) |
| Connections | People you follow |
| Lines | Groups/communities |
| Circuits | Discussion forums |
| Private Wire | Direct messages |
| Wire | A post/message |
| Crew | Other users |
| Discover | Find new content/users |

#### Features to Test

| Feature | URL | What to Test |
|---------|-----|--------------|
| Telegraph Office | `/app/telegraph` | Main social feed |
| Connections | `/app/social/connections` | Follow/unfollow users |
| Lines (Groups) | `/app/social/lines` | Join/leave groups |
| Circuits (Forums) | `/app/social/circuits` | Forum discussions |
| New Circuit Thread | `/app/social/circuits/new` | Create forum post |
| Circuit Thread | `/app/social/circuits/thread/{Id}` | View/reply to thread |
| Private Wire (DMs) | `/app/private-wire` | Direct messaging |
| My Wires | `/app/social/my-wires` | Your posts |
| Wire Detail | `/app/social/wire/{Id}` | Single post view |
| Edit Wire | `/app/social/wires/{Id}/edit` | Edit your post |
| Crew Profile | `/app/social/crew/{UserId}` | View user profile |
| Discover | `/app/social/discover` | Find users/content |
| Messages | `/app/social/messages` | Message inbox |

**Test Scenarios:**
- [ ] Create a new post (Wire)
- [ ] Like/unlike a post
- [ ] Comment on a post
- [ ] Follow another user
- [ ] View someone's profile (Crew Card)
- [ ] Create a new Line (group)
- [ ] Post in a Circuit (forum)
- [ ] Reply to a Circuit thread
- [ ] Send a Private Wire (DM)
- [ ] Edit one of your wires
- [ ] Use Discover to find new users
- [ ] View notification when someone interacts with your post

---

### 9. Marketplace

**Main URL:** `/app/marketplace`

Buy, sell, and auction model railroad equipment.

| Feature | URL | What to Test |
|---------|-----|--------------|
| Browse Listings | `/app/marketplace` | View all listings |
| Create Listing | `/app/marketplace/create` | List item for sale |
| Create Auction | `/app/marketplace/create-auction` | Start an auction |
| Auction Detail | `/app/marketplace/auction/{Id}` | View auction |
| My Listings | `/app/marketplace/my-listings` | Manage your listings |
| Purchases | `/app/marketplace/purchases` | Purchase history |
| Sales | `/app/marketplace/sales` | Sales history |
| Saved Searches | `/app/marketplace/saved-searches` | Your saved searches |
| Checkout | `/app/marketplace/{Id}/checkout` | Purchase flow |

**Test Scenarios:**
- [ ] Browse marketplace listings
- [ ] Create a fixed-price listing
- [ ] Create an auction listing
- [ ] Edit a listing
- [ ] End/cancel a listing
- [ ] Save a search
- [ ] Filter by category/price/condition
- [ ] Place a bid on auction (if available)

---

### 10. Wishlist

**Main URL:** `/app/wishlist`

Track items you want to acquire.

| Feature | URL | What to Test |
|---------|-----|--------------|
| My Wishlist | `/app/wishlist` | View wishlist items |
| Wishlist Items | `/app/wishlist/items` | Item list view |
| Add Item | `/app/wishlist/create` | Add new wishlist item |
| Item Detail | `/app/wishlist/{Id}` | View item details |
| Share Wishlist | `/app/wishlist/shared` | Share with others |
| Import | `/app/wishlist/import` | Import wishlist |
| Recommendations | `/app/wishlist/recommendations` | AI suggestions |
| Analytics | `/app/wishlist/analytics` | Wishlist stats |

**Test Scenarios:**
- [ ] Add item to wishlist manually
- [ ] Set priority level
- [ ] Add from marketplace listing
- [ ] Share wishlist publicly
- [ ] View public wishlist (`/wishlist/public/{Slug}`)
- [ ] Mark item as acquired
- [ ] Delete wishlist item

---

### 11. Operations & Gaming

**Main URL:** `/app/operations`

Model railroad operations simulation.

| Feature | URL | What to Test |
|---------|-----|--------------|
| Operations Hub | `/app/operations` | Main dashboard |
| Daily Operations | `/app/operations/daily` | Today's session |
| Session History | `/app/operations/history` | Past sessions |
| Layouts | `/app/operations/layouts` | Track plans |
| Create Layout | `/app/operations/layouts/create` | New layout |
| Layout Detail | `/app/operations/layouts/{Id}` | View layout |
| Trains | `/app/operations/trains` | Operating consists |
| Create Train | `/app/operations/trains/{LayoutId}/create` | New train |
| Practice Puzzles | `/app/operations/practice` | Switching puzzles |
| Achievements | `/app/operations/achievements` | Earned badges |
| Leaderboard | `/app/operations/leaderboard` | Rankings |
| Statistics | `/app/operations/statistics` | Your stats |

**Test Scenarios:**
- [ ] Create a new layout
- [ ] Add rolling stock to a train consist
- [ ] Start a practice puzzle
- [ ] Complete a puzzle and check score
- [ ] View achievements
- [ ] Check leaderboard position

---

### 12. Settings & Profile

**Main URL:** `/app/settings`

| Section | URL | What to Configure |
|---------|-----|-------------------|
| Profile | `/app/profile` | Display name, avatar, bio |
| Railroad | `/app/settings/railroad` | Railroad name, era, scale |
| Notifications | `/app/settings/notifications` | Email/push preferences |
| Privacy | `/app/settings/privacy` | Profile visibility |
| Theme | `/app/settings/theme` | Light/dark/terminal mode |
| Team | `/app/team` | Organization members |
| Team Member | `/app/team/{MembershipId}` | Member details |
| Public Page | `/app/settings/public-page` | Public profile customization |
| Export | `/app/settings/export` | Data export options |
| Loan Policy | `/app/settings/loan-policy` | Equipment loan settings |
| JMRI Integration | `/app/settings/integrations/jmri` | JMRI roster sync |

**Test Scenarios:**
- [ ] Update profile photo
- [ ] Change display name
- [ ] Configure railroad profile
- [ ] Toggle notification settings
- [ ] Change theme (light/dark)
- [ ] Invite team member
- [ ] Configure public page settings

---

### 13. Subscription & Billing

**Main URL:** `/app/subscription`

| Feature | URL | What to Test |
|---------|-----|--------------|
| Subscription Status | `/app/subscription` | Current plan |
| Billing | `/app/subscription/billing` | Payment info |
| Billing History | `/app/subscription/billing-history` | Invoice history |
| Payment Methods | `/app/subscription/payment-methods` | Card management |
| Usage | `/app/subscription/usage` | Feature usage |
| Upgrade | `/app/subscription/upgrade` | Plan comparison |
| Cancel | `/app/subscription/cancel` | Cancellation flow |

**Gift Subscriptions:**
| Feature | URL | What to Test |
|---------|-----|--------------|
| Purchase Gift | `/billing/gift-purchase` | Buy gift subscription |
| Gift Success | `/billing/gift-success` | Purchase confirmation |
| Manage Gifts | `/billing/gift-manage` | View sent gifts |
| Claim Gift | `/claim-gift` | Redeem gift code |
| Redeem Code | `/redeem/{Code}` | Apply promo/gift code |

**Test Scenarios:**
- [ ] View current plan details
- [ ] Check feature usage (items, photos, etc.)
- [ ] View billing history
- [ ] Attempt upgrade flow (test mode)
- [ ] Purchase gift subscription flow
- [ ] Redeem a gift code

---

## Mobile Testing

Test on phone or use browser dev tools (F12 > Toggle Device).

### Mobile Bottom Navigation

The mobile bottom bar has 5 tabs:
1. **Telegraph** - Social feed (includes Main Line, Connections, Lines, Circuits, Private Wire)
2. **Assets** - Asset management (includes Photos, Maintenance, Documents, Locations, Kits)
3. **Scan** - QR/barcode scanner (`/app/scan`)
4. **Market** - Marketplace (includes Valuations, Wishlist)
5. **More** - Everything else (Workspace, Profile, Settings, Subscription, Clubs, Museums, Operations)

### Mobile-Specific URLs

| Feature | URL | Description |
|---------|-----|-------------|
| Mobile Asset List | `/app/assets/mobile` | Optimized asset list |
| Mobile Asset Detail | `/app/asset/mobile/{Id}` | Mobile detail view |
| Mobile Add | `/app/asset/add` | Mobile add selector |
| Mobile Quick Add | `/app/asset/add/quick` | Fast entry on mobile |
| Mobile Marketplace | `/app/marketplace/mobile` | Mobile marketplace |
| Mobile Messages | `/app/messages` | Mobile message inbox |
| Mobile Conversation | `/app/messages/{Id}` | Mobile chat view |

**Test Scenarios:**
- [ ] All 5 bottom tabs work
- [ ] Hamburger menu opens full navigation
- [ ] Asset list is scrollable
- [ ] Photo upload works from camera
- [ ] Forms are usable on small screen
- [ ] Keyboard doesn't cover input fields
- [ ] QR scanner opens camera correctly

---

## Terminal Mode (Retro UI)

Experience the retro IBM 3270 mainframe aesthetic!

**Enable:** Settings > Theme > Terminal Mode

### Terminal URLs

| Feature | URL | Description |
|---------|-----|-------------|
| Telegraph | `/app/terminal/social/telegraph` | Terminal feed |
| Telegraph Office | `/app/terminal/social/office` | Terminal office |
| Circuits | `/app/terminal/social/circuits` | Terminal forums |
| New Circuit | `/app/terminal/social/circuits/new` | Create thread |
| Circuit Thread | `/app/terminal/social/circuits/thread/{Id}` | View thread |
| Connections | `/app/terminal/social/connections` | Terminal connections |
| Lines | `/app/terminal/social/lines` | Terminal lines |
| My Wires | `/app/terminal/social/my-wires` | Terminal posts |
| Wire Detail | `/app/terminal/social/wire/{Id}` | Terminal post view |
| Private Wire | `/app/terminal/social/private-wire` | Terminal DMs |
| Messages | `/app/terminal/social/messages` | Terminal inbox |
| Crew Card | `/app/terminal/social/crew/{UserId}` | Terminal profile |
| Demo | `/app/terminal-demo` | Terminal mode demo |

**Test Scenarios:**
- [ ] Terminal mode renders correctly
- [ ] Phosphor color options work (green/amber/white)
- [ ] Can switch back to modern mode (F12 key or button)
- [ ] All terminal pages are functional
- [ ] Text is readable on dark background

---

## System Alerts & Banners

RailScanPro has a system-wide alert system for announcements.

**What to Look For:**
- Emergency alerts (red banner, cannot dismiss)
- Maintenance notices (amber banner)
- Feature announcements (blue banner, dismissible)
- Release notes (injected in feed)

**Test Scenarios:**
- [ ] System banner appears at top of page when active
- [ ] Dismissible alerts can be closed
- [ ] Alert action buttons work (e.g., "Learn More")
- [ ] Dismissed alerts stay dismissed during session

---

## Admin Panel (Admin Users Only)

**Main URL:** `/app/admin`

If you have admin access, test these features:

### Core Admin Pages

| Feature | URL | What to Test |
|---------|-----|--------------|
| Admin Dashboard | `/app/admin` | Overview stats |
| Control Plane | `/app/admin/control-plane` | System controls |
| System Settings | `/app/admin/system-settings` | Configuration |
| System Messages | `/app/admin/system-messages` | Announcements |

### User & Org Management

| Feature | URL | What to Test |
|---------|-----|--------------|
| Users | `/app/admin/users` | User list |
| User Detail | `/app/admin/users/{Id}` | User management |
| Organizations | `/app/admin/organizations` | Org management |
| Invitations | `/app/admin/invitations` | Pending invites |
| Waitlist | `/app/admin/waitlist-activation` | Waitlist management |

### Subscription & Billing

| Feature | URL | What to Test |
|---------|-----|--------------|
| Plans | `/app/admin/plans` | Subscription plans |
| FinOps | `/app/admin/finops` | Financial ops |
| Stripe | `/app/admin/stripe` | Stripe settings |

### Monitoring & Health

| Feature | URL | What to Test |
|---------|-----|--------------|
| Health | `/app/admin/health` | System health |
| Analytics | `/app/admin/analytics` | Usage analytics |
| Observability | `/app/admin/observability` | Traces/metrics |
| Errors | `/app/admin/errors` | Error tracking |
| Audit | `/app/admin/audit` | Audit log |
| Jobs | `/app/admin/jobs` | Background job history |
| Functions | `/app/admin/functions` | Azure Functions |

### Content & Moderation

| Feature | URL | What to Test |
|---------|-----|--------------|
| Bug Reports | `/app/admin/bug-reports` | User bug reports |
| Feature Requests | `/app/admin/feature-requests` | User suggestions |
| Moderation | `/app/admin/moderation` | Content moderation |
| Blocklist | `/app/admin/blocklist` | Blocked users/content |
| Blog | `/app/admin/blog` | Blog management |
| Feedback Analytics | `/app/admin/feedback-analytics` | Feedback stats |
| Survey Responses | `/app/admin/survey-responses` | Survey results |

### Data & Configuration

| Feature | URL | What to Test |
|---------|-----|--------------|
| Features | `/app/admin/features` | Feature flags |
| Taxonomy | `/app/admin/taxonomy` | Category management |
| Lookups | `/app/admin/lookups` | Lookup tables |
| Data Pipeline | `/app/admin/data-pipeline` | Import jobs |
| Prompt Management | `/app/admin/prompt-management` | AI prompts |
| Railroad History | `/app/admin/railroad-history` | Historical events |
| Puzzle Generator | `/app/admin/puzzle-generator` | Create puzzles |
| TrainController Import | `/app/admin/import-traincontroller` | Legacy import |

**Admin Test Scenarios:**
- [ ] Admin dashboard loads with stats
- [ ] Can view user list and details
- [ ] Can create/edit system messages
- [ ] Can view error logs
- [ ] Can manage feature flags
- [ ] Health check shows all services
- [ ] Background jobs history displays

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
- Terminal Mode: [Yes/No]
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

**In-App Feedback:**
- Report Bug: `/app/feedback/report-bug`
- Feature Board: `/app/feedback/features`
- My Bug Reports: `/app/feedback/my-bugs`

**Questions?** Contact the development team or submit feedback using the links above.

Happy testing!
