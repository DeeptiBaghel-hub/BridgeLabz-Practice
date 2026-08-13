
# 🎨 Dashboard UI — HTML & CSS

A beginner-friendly dashboard UI created from a visual reference using **HTML and CSS**.

The purpose of this project is to learn how to break a design into smaller parts and build each part using HTML structure and CSS styling.

---

## 📸 Project Preview

The dashboard is divided into four main areas:

```text
┌──────────────────────────────────────────────────────┐
│                      HEADER                          │
│  Logo    Navigation              Search       ○      │
├──────────┬───────────────────────────────────────────┤
│          │                                           │
│ SIDEBAR  │       ┌──────┐ ┌──────┐ ┌──────┐        │
│          │       │ CARD │ │ CARD │ │ CARD │        │
│   ▬     │       └──────┘ └──────┘ └──────┘        │
│   ▬     │                                           │
│   ▬     │                  ─────                    │
│   ▬     │                   ───                     │
│          │                    ─                      │
├──────────┴───────────────────────────────────────────┤
│                       FOOTER                         │
└──────────────────────────────────────────────────────┘
```

---

# 📁 Project Structure

The project contains only three files:

```text
dashboard/
│
├── index.html
├── style.css
└── README.md
```

| File         | Purpose                                |
| ------------ | -------------------------------------- |
| `index.html` | Creates the structure of the dashboard |
| `style.css`  | Controls the design and layout         |
| `README.md`  | Explains the project                   |

---

# 🏗️ HTML Structure

The HTML is organized like a tree.

```text
body
│
└── dashboard
    │
    ├── header
    │   ├── logo
    │   ├── nav
    │   ├── search
    │   └── profile
    │
    ├── main
    │   │
    │   ├── sidebar
    │   │   └── side-item
    │   │
    │   └── content
    │       │
    │       ├── cards
    │       │   ├── card
    │       │   ├── card
    │       │   └── card
    │       │
    │       └── stats
    │           ├── stat
    │           ├── stat
    │           └── stat
    │
    └── footer
        ├── footer-item
        ├── footer-item
        ├── footer-item
        ├── footer-item
        └── footer-item
```

---

# 🧩 HTML Element Table

This table explains what each class does.

| HTML Class     | What it represents       | Parent       | Children                   |
| -------------- | ------------------------ | ------------ | -------------------------- |
| `.dashboard`   | Main dashboard container | `body`       | Header, Main, Footer       |
| `.header`      | Pink top section         | `.dashboard` | Logo, Nav, Search, Profile |
| `.logo`        | Circular logo            | `.header`    | None                       |
| `.nav`         | Navigation area          | `.header`    | 3 `<span>` elements        |
| `.search`      | Search box               | `.header`    | None                       |
| `.profile`     | Profile circle           | `.header`    | None                       |
| `.main`        | Main dashboard area      | `.dashboard` | Sidebar, Content           |
| `.sidebar`     | Left navigation panel    | `.main`      | Side items                 |
| `.side-item`   | Sidebar menu item        | `.sidebar`   | None                       |
| `.content`     | Main content area        | `.main`      | Cards, Stats               |
| `.cards`       | Container for cards      | `.content`   | 3 Cards                    |
| `.card`        | Dashboard card           | `.cards`     | None                       |
| `.stats`       | Statistics container     | `.content`   | 3 Stats                    |
| `.stat`        | Individual statistic bar | `.stats`     | None                       |
| `.footer`      | Bottom section           | `.dashboard` | Footer items               |
| `.footer-item` | Footer element           | `.footer`    | None                       |

---

# 🎨 CSS Structure

The CSS follows the same structure as the HTML.

```text
CSS
│
├── Global Styles
│
├── Body
│
├── Dashboard
│
├── Header
│   ├── Logo
│   ├── Navigation
│   ├── Search
│   └── Profile
│
├── Main
│   ├── Sidebar
│   ├── Side Items
│   └── Content
│       ├── Cards
│       └── Stats
│
└── Footer
    └── Footer Items
```

---

# 📊 HTML → CSS Relationship

This is one of the most important things to understand.

| HTML                      | CSS             | What happens              |
| ------------------------- | --------------- | ------------------------- |
| `<div class="dashboard">` | `.dashboard {}` | Styles the main dashboard |
| `<div class="header">`    | `.header {}`    | Creates the header        |
| `<div class="logo">`      | `.logo {}`      | Creates the logo circle   |
| `<div class="nav">`       | `.nav {}`       | Arranges navigation items |
| `<div class="search">`    | `.search {}`    | Creates search box        |
| `<div class="profile">`   | `.profile {}`   | Creates profile circle    |
| `<div class="main">`      | `.main {}`      | Creates main area         |
| `<div class="sidebar">`   | `.sidebar {}`   | Creates left sidebar      |
| `<div class="content">`   | `.content {}`   | Creates content area      |
| `<div class="cards">`     | `.cards {}`     | Creates card grid         |
| `<div class="card">`      | `.card {}`      | Styles each card          |
| `<div class="stats">`     | `.stats {}`     | Arranges statistics       |
| `<div class="stat">`      | `.stat {}`      | Styles statistic bars     |
| `<div class="footer">`    | `.footer {}`    | Creates bottom section    |

---

# 📐 Layout Structure

The dashboard uses two major CSS layout systems:

## 1. Flexbox

Flexbox is used for the main sections.

### Header

```css
.header {
    display: flex;
    align-items: center;
}
```

This places the header items in a row:

```text
Logo → Navigation → Search → Profile
```

### Main

```css
.main {
    display: flex;
}
```

This places the sidebar and content next to each other:

```text
Sidebar | Content
```

### Footer

```css
.footer {
    display: flex;
    align-items: center;
}
```

This places footer items in a row.

---

# 2. CSS Grid

Grid is used for the three cards.

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 20px;
}
```

This creates:

```text
┌────────┐  ┌────────┐  ┌────────┐
│  CARD  │  │  CARD  │  │  CARD  │
└────────┘  └────────┘  └────────┘
```

### What does `repeat(3, 1fr)` mean?

It means:

> Create 3 equal columns.

So:

```text
1fr | 1fr | 1fr
```

Each column gets an equal amount of space.

---

# 📦 Box Model

Every HTML element can be thought of as a box.

```text
┌─────────────────────────────┐
│           MARGIN            │
│  ┌───────────────────────┐  │
│  │        BORDER         │  │
│  │  ┌─────────────────┐  │  │
│  │  │     PADDING     │  │  │
│  │  │  ┌───────────┐  │  │  │
│  │  │  │  CONTENT  │  │  │  │
│  │  │  └───────────┘  │  │  │
│  │  └─────────────────┘  │  │
│  └───────────────────────┘  │
└─────────────────────────────┘
```

The project uses:

| Property        | Meaning                   |
| --------------- | ------------------------- |
| `width`         | Element width             |
| `height`        | Element height            |
| `padding`       | Space inside the element  |
| `margin`        | Space outside the element |
| `border`        | Line around the element   |
| `border-radius` | Makes corners rounded     |
| `box-shadow`    | Adds a shadow             |

---

# 🎯 Important CSS Properties Used

| CSS Property    | Example               | Purpose                            |
| --------------- | --------------------- | ---------------------------------- |
| `display: flex` | `.main`               | Creates a Flexbox layout           |
| `display: grid` | `.cards`              | Creates a grid layout              |
| `width`         | `width: 850px`        | Controls width                     |
| `height`        | `height: 500px`       | Controls height                    |
| `background`    | `background: #514b59` | Sets background color              |
| `padding`       | `padding: 25px`       | Adds inside spacing                |
| `margin`        | `margin-left: 20px`   | Adds outside spacing               |
| `gap`           | `gap: 20px`           | Adds space between flex/grid items |
| `border-radius` | `border-radius: 14px` | Rounds corners                     |
| `box-shadow`    | `box-shadow: ...`     | Adds shadow                        |
| `position`      | `position: relative`  | Controls positioning               |
| `flex`          | `flex: 1`             | Takes remaining available space    |

---

# 🪜 Step-by-Step Development

The project was created in the following order.

## Step 1 — Create the project folder

```text
dashboard/
```

---

## Step 2 — Create the files

```text
dashboard/
├── index.html
├── style.css
└── README.md
```

---

## Step 3 — Create the basic HTML

```html
<!DOCTYPE html>
<html lang="en">

<head>
    <title>My Dashboard</title>
    <link rel="stylesheet" href="style.css">
</head>

<body>

</body>

</html>
```

---

## Step 4 — Create the dashboard

```html
<div class="dashboard">

</div>
```

Then CSS:

```css
.dashboard {
    width: 850px;
    height: 500px;
}
```

---

## Step 5 — Add the header

```text
Dashboard
└── Header
    ├── Logo
    ├── Navigation
    ├── Search
    └── Profile
```

---

## Step 6 — Add the main area

```text
Main
├── Sidebar
└── Content
```

Flexbox is used here:

```css
.main {
    display: flex;
}
```

---

## Step 7 — Add the sidebar

```text
Sidebar
├── Item
├── Item
├── Item
├── Item
├── Item
└── Item
```

---

## Step 8 — Add the cards

```text
Content
└── Cards
    ├── Card
    ├── Card
    └── Card
```

CSS Grid is used:

```css
.cards {
    display: grid;
    grid-template-columns: repeat(3, 1fr);
}
```

---

## Step 9 — Add statistics

```text
Stats
├── Stat
├── Stat
└── Stat
```

---

## Step 10 — Add the footer

```text
Footer
├── Item
├── Item
├── Item
├── Item
└── Item
```

---

# 🔄 How HTML and CSS Work Together

The basic workflow is:

```text
          HTML
           ↓
     Create an element
           ↓
      Give it a class
           ↓
          CSS
           ↓
      Select the class
           ↓
    Add styling & layout
           ↓
      Browser renders it
```

For example:

### HTML

```html
<div class="card"></div>
```

### CSS

```css
.card {
    width: 200px;
    height: 100px;
    background: white;
    border-radius: 14px;
}
```

### Result

```text
┌────────────────────┐
│                    │
│       CARD         │
│                    │
└────────────────────┘
```

---

# 🚀 Running the Project

## Option 1 — Open directly

Double-click:

```text
index.html
```

Your browser will open the dashboard.

---

## Option 2 — VS Code Live Server

Install the **Live Server** extension in VS Code.

Then:

1. Open `index.html`
2. Right-click the file
3. Select **Open with Live Server**
4. The website opens in your browser

Live Server automatically refreshes the page when you save changes.

---

# 🌱 What I Learned

This project helped practice:

* HTML document structure
* HTML classes
* Parent and child elements
* CSS selectors
* CSS box model
* Flexbox
* CSS Grid
* Width and height
* Margin and padding
* `gap`
* Colors
* Borders
* Border radius
* Box shadows
* Relative and absolute positioning
* Creating a layout from a visual reference
* Organizing a frontend project

---

# 🔮 Future Improvements

Possible improvements:

* [ ] Make the dashboard responsive
* [ ] Add real navigation links
* [ ] Add icons
* [ ] Add hover effects
* [ ] Add JavaScript interactions
* [ ] Add real dashboard data
* [ ] Add dark/light mode
* [ ] Add animations
* [ ] Improve mobile layout

---

# 📚 Learning Path

After completing this project, the recommended learning path is:

```text
HTML Basics
     ↓
CSS Basics
     ↓
Box Model
     ↓
Flexbox
     ↓
CSS Grid
     ↓
Positioning
     ↓
Responsive Design
     ↓
JavaScript
     ↓
DOM Manipulation
     ↓
Interactive Websites
```

---

# 📌 Beginner Summary

Remember these three things:

### HTML = Structure

```text
What exists?
```

### CSS = Design

```text
How does it look?
```

### Flexbox/Grid = Layout

```text
Where does it go?
```

Together:

```text
HTML
  +
CSS
  +
Flexbox / Grid
  =
Webpage
```

---

## 📄 License

This project was created for learning and practice purposes.
