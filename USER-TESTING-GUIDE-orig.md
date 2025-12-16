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

"USER-TESTING-GUIDE.md" [readonly] 437L, 12258B
