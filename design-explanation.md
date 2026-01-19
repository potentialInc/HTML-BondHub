# BondHub - Design Decisions & User Flow

## Project Overview

BondHub is a community-based social networking platform where users can join interest-based communities, share posts, engage in discussions, and connect with like-minded individuals. The platform serves three user types: **Public visitors**, **Registered users**, and **Administrators**.

---

## Screen Overview

### Authentication Pages (4 screens)

| # | Screen | Purpose | Local | Live |
|---|--------|---------|-------|------|
| 1 | [Login](#1-login) | User authentication | [02-login.html](./02-login.html) | [Live](https://potentialinc.github.io/HTML-BondHub/02-login.html) |
| 2 | [Sign Up](#2-sign-up) | New user registration | [03-signup.html](./03-signup.html) | [Live](https://potentialinc.github.io/HTML-BondHub/03-signup.html) |
| 3 | [Forgot Password](#3-forgot-password) | Password recovery | [04-forgot-password.html](./04-forgot-password.html) | [Live](https://potentialinc.github.io/HTML-BondHub/04-forgot-password.html) |
| 4 | [Admin Login](#4-admin-login) | Admin authentication | [15-admin-login.html](./15-admin-login.html) | [Live](https://potentialinc.github.io/HTML-BondHub/15-admin-login.html) |

### User App Pages (10 screens)

| # | Screen | Purpose | Local | Live |
|---|--------|---------|-------|------|
| 5 | [Home Feed](#5-home-feed) | Main content feed | [05-home-feed.html](./05-home-feed.html) | [Live](https://potentialinc.github.io/HTML-BondHub/05-home-feed.html) |
| 6 | [Post Detail](#6-post-detail) | Single post view | [06-post-detail.html](./06-post-detail.html) | [Live](https://potentialinc.github.io/HTML-BondHub/06-post-detail.html) |
| 7 | [Community List](#7-community-list) | Browse communities | [07-community-list.html](./07-community-list.html) | [Live](https://potentialinc.github.io/HTML-BondHub/07-community-list.html) |
| 8 | [Community Detail](#8-community-detail) | Single community view | [08-community-detail.html](./08-community-detail.html) | [Live](https://potentialinc.github.io/HTML-BondHub/08-community-detail.html) |
| 9 | [Create Post](#9-create-post) | Create new post | [09-create-post.html](./09-create-post.html) | [Live](https://potentialinc.github.io/HTML-BondHub/09-create-post.html) |
| 10 | [My Profile](#10-my-profile) | User's own profile | [10-my-profile.html](./10-my-profile.html) | [Live](https://potentialinc.github.io/HTML-BondHub/10-my-profile.html) |
| 11 | [Edit Profile](#11-edit-profile) | Edit user profile | [11-edit-profile.html](./11-edit-profile.html) | [Live](https://potentialinc.github.io/HTML-BondHub/11-edit-profile.html) |
| 12 | [Following List](#12-following-list) | View following/followers | [12-following-list.html](./12-following-list.html) | [Live](https://potentialinc.github.io/HTML-BondHub/12-following-list.html) |
| 13 | [Other User Profile](#13-other-user-profile) | View another user's profile | [13-other-user-profile.html](./13-other-user-profile.html) | [Live](https://potentialinc.github.io/HTML-BondHub/13-other-user-profile.html) |
| 14 | [Settings](#14-settings) | User settings | [14-settings.html](./14-settings.html) | [Live](https://potentialinc.github.io/HTML-BondHub/14-settings.html) |

### Admin Pages (7 screens)

| # | Screen | Purpose | Local | Live |
|---|--------|---------|-------|------|
| 15 | [Admin Dashboard](#15-admin-dashboard) | Platform overview | [16-admin-dashboard.html](./16-admin-dashboard.html) | [Live](https://potentialinc.github.io/HTML-BondHub/16-admin-dashboard.html) |
| 16 | [User Management](#16-user-management) | Manage users | [17-user-management.html](./17-user-management.html) | [Live](https://potentialinc.github.io/HTML-BondHub/17-user-management.html) |
| 17 | [Community Management](#17-community-management) | Manage communities | [18-community-management.html](./18-community-management.html) | [Live](https://potentialinc.github.io/HTML-BondHub/18-community-management.html) |
| 18 | [Post Management](#18-post-management) | Moderate posts | [19-post-management.html](./19-post-management.html) | [Live](https://potentialinc.github.io/HTML-BondHub/19-post-management.html) |
| 19 | [Comment Management](#19-comment-management) | Moderate comments | [20-comment-management.html](./20-comment-management.html) | [Live](https://potentialinc.github.io/HTML-BondHub/20-comment-management.html) |
| 20 | [Data Export](#20-data-export) | Export platform data | [21-data-export.html](./21-data-export.html) | [Live](https://potentialinc.github.io/HTML-BondHub/21-data-export.html) |
| 21 | [Admin Settings](#21-admin-settings) | Admin account settings | [22-admin-settings.html](./22-admin-settings.html) | [Live](https://potentialinc.github.io/HTML-BondHub/22-admin-settings.html) |

---

## User Flow Diagrams

### Public User Journey

```
[Login Page: 02-login.html]
         │
         ├──► Enter credentials ──► [05-home-feed.html]
         │
         ├──► Click "Forgot Password" ──► [04-forgot-password.html]
         │
         └──► Click "Sign Up" ──► [03-signup.html]
                                      │
                                      └──► Complete registration ──► [02-login.html]
```

### Registered User Journey

```
[02-login.html] ──► Enter credentials ──► [05-home-feed.html]
                                                │
         ┌──────────────────────────────────────┼──────────────────────────────────────┐
         │                    │                 │                 │                    │
         ▼                    ▼                 ▼                 ▼                    ▼
   Browse Feed          Communities        My Profile        Create Post          Settings
         │                    │                 │                 │                    │
         ▼                    ▼                 ▼                 ▼                    ▼
   Click post ──►    [07-community-    [10-my-profile.   [09-create-post.    [14-settings.
   [06-post-detail]     list.html]         html]             html]              html]
                          │                   │
                          ▼                   ├──► Edit Profile ──► [11-edit-profile.html]
                    Click community           │
                          │                   └──► Following/Followers ──► [12-following-list.html]
                          ▼
                    [08-community-detail.html]
```

### Admin Journey

```
[15-admin-login.html] ──► Admin credentials ──► [16-admin-dashboard.html]
                                                        │
    ┌─────────┬─────────┬─────────┬──────────┬──────────┼──────────┐
    │         │         │         │          │          │          │
    ▼         ▼         ▼         ▼          ▼          ▼          ▼
 Stats     Users    Communities  Posts    Comments   Export    Settings
    │         │         │         │          │          │          │
    │         ▼         ▼         ▼          ▼          ▼          ▼
    │  [17-user-  [18-community- [19-post- [20-comment- [21-data- [22-admin-
    │  management] management]  management] management] export]  settings]
    │
    └──► View platform metrics and recent activity
```

---

## Screen-by-Screen Design Decisions

### 1. Login
**File:** [02-login.html](./02-login.html)

**Design Decisions:**
- **Split Screen Layout**: Brand messaging/visual on left, form on right - balances branding with utility
- **Centered Form**: Clean, minimal form focused on email and password
- **Password Toggle**: Eye icon to show/hide password for usability
- **Social Context**: Subtle brand reinforcement through color and iconography
- **"Forgot Password" Link**: Positioned below password field for easy access
- **Sign Up Prompt**: Clear CTA for new users at bottom

**Demo Account:**
- Email: `demo@demo.com` / Password: `1234` → Redirects to [05-home-feed.html](./05-home-feed.html)

**Why These Choices:**
- Minimal form fields reduce friction
- Split layout works well on desktop, collapses on mobile
- Password visibility toggle is expected by modern users

---

### 2. Sign Up
**File:** [03-signup.html](./03-signup.html)

**Design Decisions:**
- **Consistent Split Layout**: Matches login page for visual consistency
- **Multi-Field Form**: Full name, email, password, confirm password
- **Password Requirements**: Clear validation indicators
- **Terms Agreement**: Checkbox for legal compliance
- **Login Link**: For existing users who landed here by mistake

**Why These Choices:**
- Consistent design patterns across auth flows
- All required fields visible upfront
- Password confirmation prevents typos

---

### 3. Forgot Password
**File:** [04-forgot-password.html](./04-forgot-password.html)

**Design Decisions:**
- **Single Email Field**: Minimal friction for recovery
- **Clear Instructions**: Explains what will happen after submission
- **Back to Login Link**: Easy return path
- **Consistent Layout**: Matches other auth pages

**Why These Choices:**
- Simple flow reduces user frustration
- Clear messaging sets expectations
- Consistent experience across auth pages

---

### 4. Admin Login
**File:** [15-admin-login.html](./15-admin-login.html)

**Design Decisions:**
- **Dark Theme**: Distinct from user login, signals admin area
- **Centered Card**: Focused form on dark background
- **Security Badge**: "BondHub Admin" branding with shield icon
- **Security Notice**: "Protected by BondHub Security" footer text
- **Minimal Form**: Email and password only

**Demo Account:**
- Email: `admin@bondhub.com` / Password: `admin1234` → Redirects to [16-admin-dashboard.html](./16-admin-dashboard.html)

**Why These Choices:**
- Dark theme creates visual separation from user app
- Security messaging reinforces admin authority
- Minimal design reduces distraction

---

### 5. Home Feed
**File:** [05-home-feed.html](./05-home-feed.html)

**Design Decisions:**
- **Fixed Sidebar Navigation**: Persistent access to main sections (Home, Communities, Profile, Settings)
- **Content-Focused Layout**: Wide content area for posts
- **Post Cards**: Author avatar, content preview, engagement metrics
- **Right Sidebar**: Trending topics, suggested communities, who to follow
- **Mobile Bottom Nav**: Fixed navigation for mobile devices
- **Create Post Button**: Prominent CTA in sidebar

**Navigation Items:**
- Home → [05-home-feed.html](./05-home-feed.html)
- Communities → [07-community-list.html](./07-community-list.html)
- Profile → [10-my-profile.html](./10-my-profile.html)
- Settings → [14-settings.html](./14-settings.html)

**Why These Choices:**
- Familiar social media layout users expect
- Sidebar keeps navigation always accessible
- Right sidebar adds discovery without cluttering feed
- Mobile nav ensures key actions are reachable with thumb

---

### 6. Post Detail
**File:** [06-post-detail.html](./06-post-detail.html)

**Design Decisions:**
- **Full Post Content**: Complete text and media display
- **Author Info**: Avatar, name, username, timestamp
- **Engagement Actions**: Like, comment, share, bookmark
- **Comments Section**: Threaded replies with author info
- **Related Posts**: Suggestions for continued engagement
- **Back Navigation**: Easy return to feed

**Why These Choices:**
- Full content display for detailed reading
- Threaded comments enable meaningful discussions
- Related posts increase session duration

---

### 7. Community List
**File:** [07-community-list.html](./07-community-list.html)

**Design Decisions:**
- **Grid Layout**: Community cards in responsive grid
- **Search Bar**: Find communities by name
- **Category Filter**: Filter by interest category
- **Community Cards**: Cover image, name, member count, description preview
- **Join Button**: Quick action to join communities
- **Sidebar Navigation**: Consistent with home feed

**Why These Choices:**
- Grid enables visual scanning of many communities
- Search and filter help users find relevant groups
- Quick join reduces friction to membership

---

### 8. Community Detail
**File:** [08-community-detail.html](./08-community-detail.html)

**Design Decisions:**
- **Hero Banner**: Community cover image and branding
- **Community Info**: Name, description, member count, rules
- **Tabbed Content**: Posts, About, Members, Media tabs
- **Post Feed**: Community-specific posts
- **Join/Leave Button**: Membership toggle
- **Admin Badge**: Indicates community moderators

**Why These Choices:**
- Hero creates community identity
- Tabs organize different content types
- Prominent join button encourages membership

---

### 9. Create Post
**File:** [09-create-post.html](./09-create-post.html)

**Design Decisions:**
- **Rich Text Editor**: Formatting options for post content
- **Community Selector**: Choose which community to post in
- **Media Upload**: Drag and drop or click to upload images
- **Preview Mode**: See post before publishing
- **Draft/Publish Actions**: Save progress or publish immediately

**Why These Choices:**
- Rich text enables expressive posts
- Community selection organizes content
- Preview prevents mistakes

---

### 10. My Profile
**File:** [10-my-profile.html](./10-my-profile.html)

**Design Decisions:**
- **Profile Header**: Cover image, avatar, name, bio
- **Stats Display**: Posts, followers, following counts
- **Edit Profile Button**: Quick access to edit
- **Content Tabs**: Posts, Replies, Media, Likes
- **Activity Feed**: User's posts and interactions

**Why These Choices:**
- Standard profile layout users expect
- Stats create social proof
- Tabs organize different content types

---

### 11. Edit Profile
**File:** [11-edit-profile.html](./11-edit-profile.html)

**Design Decisions:**
- **Avatar Upload**: Change profile picture
- **Cover Image Upload**: Change banner image
- **Form Fields**: Name, bio, location, website
- **Save/Cancel Actions**: Clear action buttons
- **Preview**: See changes before saving

**Why These Choices:**
- All editable fields in one place
- Image upload is drag and drop
- Preview prevents unintended changes

---

### 12. Following List
**File:** [12-following-list.html](./12-following-list.html)

**Design Decisions:**
- **Tab Toggle**: Switch between Following and Followers
- **User List**: Avatar, name, username, bio preview
- **Follow/Unfollow Button**: Quick action per user
- **Search Filter**: Find specific users

**Why These Choices:**
- Tab toggle provides both views
- List format efficient for scanning
- Quick actions reduce clicks

---

### 13. Other User Profile
**File:** [13-other-user-profile.html](./13-other-user-profile.html)

**Design Decisions:**
- **Same Layout as My Profile**: Consistent experience
- **Follow Button**: Instead of edit button
- **Message Button**: Initiate conversation
- **Mutual Followers**: Shows shared connections

**Why These Choices:**
- Consistency reduces cognitive load
- Follow and message are primary actions
- Mutual connections build trust

---

### 14. Settings
**File:** [14-settings.html](./14-settings.html)

**Design Decisions:**
- **Settings Groups**: Account, Privacy, Notifications, Appearance
- **Toggle Switches**: For on/off settings
- **Form Inputs**: For text-based settings
- **Save Confirmation**: Visual feedback on save
- **Logout Option**: Clear sign out action

**Why These Choices:**
- Grouped settings are easier to navigate
- Toggle switches are intuitive
- Immediate feedback confirms changes

---

### 15. Admin Dashboard
**File:** [16-admin-dashboard.html](./16-admin-dashboard.html)

**Design Decisions:**
- **Dark Sidebar**: Consistent admin theme
- **Stats Cards**: Total Users, Posts, Communities, Active Today
- **Trend Indicators**: Percentage changes vs previous period
- **Recent Activity Table**: Latest platform events
- **Date Range Filter**: Adjust reporting period
- **Quick Actions**: View All links to detailed pages

**Admin Sidebar Navigation:**
- Dashboard → [16-admin-dashboard.html](./16-admin-dashboard.html)
- Users → [17-user-management.html](./17-user-management.html)
- Communities → [18-community-management.html](./18-community-management.html)
- Posts → [19-post-management.html](./19-post-management.html)
- Comments → [20-comment-management.html](./20-comment-management.html)
- Analytics → [21-data-export.html](./21-data-export.html)
- Settings → [22-admin-settings.html](./22-admin-settings.html)

**Why These Choices:**
- Stats provide immediate platform health overview
- Trends show growth/decline at a glance
- Activity table surfaces recent events needing attention

---

### 16. User Management
**File:** [17-user-management.html](./17-user-management.html)

**Design Decisions:**
- **Search Bar**: Find users by name or email
- **Filter Dropdown**: Filter by role (Admin, Moderator, User)
- **Data Table**: Columns for user info, role, status, joined date
- **Status Badges**: Green "Active", Red "Suspended"
- **Action Buttons**: Edit, Suspend per row
- **Pagination**: Handle large user lists

**Why These Choices:**
- Table format efficient for user management
- Search and filter for quick access
- Inline actions reduce navigation

---

### 17. Community Management
**File:** [18-community-management.html](./18-community-management.html)

**Design Decisions:**
- **Community Table**: Name, members, posts, status, created date
- **Create Community Button**: Admin can create communities
- **Search and Filter**: Find specific communities
- **Status Toggle**: Active/Archived states
- **Action Buttons**: View, Edit, Archive, Delete

**Why These Choices:**
- Table provides quick overview
- Admin-created communities for official groups
- Status management for lifecycle control

---

### 18. Post Management
**File:** [19-post-management.html](./19-post-management.html)

**Design Decisions:**
- **Post Table**: Title, author, community, comments, flagged status, date
- **Flagged Filter**: Show flagged content first
- **Flag Type Badges**: Spam (yellow), Harassment (red)
- **Community Filter**: Filter by community
- **Action Buttons**: View, Delete

**Why These Choices:**
- Flagged content needs attention first
- Flag types help prioritize moderation
- Community filter for targeted review

---

### 19. Comment Management
**File:** [20-comment-management.html](./20-comment-management.html)

**Design Decisions:**
- **Comment Table**: Content preview, author, post title, flagged status, date
- **Flagged Filter**: Focus on reported content
- **Export Button**: Download comment data
- **Bulk Delete**: Handle multiple comments at once
- **Action Buttons**: View, Delete per row

**Why These Choices:**
- Comment preview shows context
- Bulk actions for efficiency
- Export for reporting needs

---

### 20. Data Export
**File:** [21-data-export.html](./21-data-export.html)

**Design Decisions:**
- **Data Type Selection**: Users, Communities, Posts as card options
- **Date Range**: All time or custom range
- **Format Selection**: CSV or Excel
- **Export Button**: Clear CTA
- **Success Message**: Confirmation after export

**Why These Choices:**
- Card selection is visual and clear
- Multiple formats support different tools
- Success feedback confirms completion

---

### 21. Admin Settings
**File:** [22-admin-settings.html](./22-admin-settings.html)

**Design Decisions:**
- **Account Settings Group**: Email display, change password
- **System Settings Group**: Placeholder for future settings
- **Logout Button**: Red-styled for destructive action
- **Version Display**: "BondHub Admin v2.4.0" footer

**Why These Choices:**
- Grouped settings are organized
- Logout is prominent but styled as warning
- Version info for troubleshooting

---

## Navigation Structure

### User App Navigation (Sidebar)
```
[Logo: BondHub]
       │
       ├── Home ──────────► [05-home-feed.html]
       ├── Communities ───► [07-community-list.html]
       ├── Profile ───────► [10-my-profile.html]
       └── Settings ──────► [14-settings.html]

[User Mini Profile]
       └── Avatar + Name + Username
```

### User App Navigation (Mobile Bottom)
```
[Home] ─── [Communities] ─── [Profile] ─── [Settings]
```

### Admin Navigation (Dark Sidebar)
```
[Logo: BondHub Admin]
       │
       ├── Dashboard ─────► [16-admin-dashboard.html]
       ├── Users ─────────► [17-user-management.html]
       ├── Communities ───► [18-community-management.html]
       ├── Posts ─────────► [19-post-management.html]
       ├── Comments ──────► [20-comment-management.html]
       │
       ├── [SYSTEM]
       ├── Analytics ─────► [21-data-export.html]
       └── Settings ──────► [22-admin-settings.html]

[Admin User Profile]
       └── Avatar + Name + Email
```

---

## Key Design Patterns

### 1. Color System
- **Primary Color**: Teal (#14B8A6)
- **Primary Hover**: Darker Teal (#0D9488)
- **Background**: Light Gray (#F9FAFB / gray-50)
- **Card Background**: White
- **Text Primary**: Slate Gray (#0F172A / slate-900)
- **Text Secondary**: Gray (#6B7280 / gray-500)

### 2. Status Indication
Consistent color meanings:
- **Green**: Active, Success, Online
- **Amber/Yellow**: Warning, Pending, Flagged (Spam)
- **Red**: Suspended, Error, Flagged (Harassment), Destructive actions

### 3. Card Pattern
Used throughout for posts, communities, and stats:
- White background on gray page background
- Subtle border (`border-gray-200`)
- Rounded corners (`rounded-xl`)
- Subtle shadow (`shadow-sm`)
- Hover effects for interactive cards

### 4. Sidebar Pattern
**User App:**
- 240px fixed width
- White background
- Light border right
- Logo at top
- Nav items with icons
- User profile at bottom

**Admin:**
- 240px fixed width
- Dark gray-900 background
- Teal left border on active item
- "System" divider for secondary items
- Admin profile at bottom

### 5. Mobile Adaptations
- Sidebar hidden on mobile (`hidden lg:flex`)
- Bottom navigation bar (`lg:hidden`)
- Fixed position at bottom
- Icon + label for each nav item
- Teal color for active state

### 6. Typography
- **Font Family**: Inter
- **Heading 1**: 32px, semibold
- **Body**: 14px, regular
- **Small/Caption**: 12px
- **Smooth rendering**: antialiased

### 7. Icons
- **Icon Library**: Lucide via Iconify
- **Size**: 18-20px for navigation, 16px for inline
- **Style**: Outline/stroke style
- **Consistency**: Same icon set throughout

---

## Demo Access

**Live URL:** https://potentialinc.github.io/HTML-BondHub/

**Login Credentials:**
| Role | Email | Password | Entry Point |
|------|-------|----------|-------------|
| User | `demo@demo.com` | `1234` | [02-login.html](./02-login.html) |
| Admin | `admin@bondhub.com` | `admin1234` | [15-admin-login.html](./15-admin-login.html) |

---

## File Quick Links

### Authentication Pages
- [02-login.html](./02-login.html) - User Login
- [03-signup.html](./03-signup.html) - Sign Up
- [04-forgot-password.html](./04-forgot-password.html) - Forgot Password
- [15-admin-login.html](./15-admin-login.html) - Admin Login

### User App Pages
- [05-home-feed.html](./05-home-feed.html) - Home Feed
- [06-post-detail.html](./06-post-detail.html) - Post Detail
- [07-community-list.html](./07-community-list.html) - Community List
- [08-community-detail.html](./08-community-detail.html) - Community Detail
- [09-create-post.html](./09-create-post.html) - Create Post
- [10-my-profile.html](./10-my-profile.html) - My Profile
- [11-edit-profile.html](./11-edit-profile.html) - Edit Profile
- [12-following-list.html](./12-following-list.html) - Following List
- [13-other-user-profile.html](./13-other-user-profile.html) - Other User Profile
- [14-settings.html](./14-settings.html) - Settings

### Admin Pages
- [16-admin-dashboard.html](./16-admin-dashboard.html) - Admin Dashboard
- [17-user-management.html](./17-user-management.html) - User Management
- [18-community-management.html](./18-community-management.html) - Community Management
- [19-post-management.html](./19-post-management.html) - Post Management
- [20-comment-management.html](./20-comment-management.html) - Comment Management
- [21-data-export.html](./21-data-export.html) - Data Export / Analytics
- [22-admin-settings.html](./22-admin-settings.html) - Admin Settings
