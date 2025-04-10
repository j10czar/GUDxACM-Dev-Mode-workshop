# 🎨 Figma Dev Mode Workshop Guide  
**Using Figma Dev Mode + VS Code + Live Server**

---

## ✅ Setup Instructions

### 🔧 VS Code Setup
1. Open **Visual Studio Code**
2. Create a folder (e.g., `portfolio-site`) and open it in VS Code
3. Inside that folder, create two files:
   - `index.html`
   - `style.css`

### 🧩 Assets Setup
1. Make sure you’ve downloaded the **assets folder** provided
2. Place the folder inside your project directory (same level as `index.html`)

```
portfolio-site/
├── assets/
├── index.html
└── style.css
```

### 🚀 Live Server Setup
1. In VS Code, go to the **Extensions tab**
2. Search for and install: `Live Server` by Ritwick Dey
3. Right-click `index.html` and click **"Open with Live Server"**
4. Your browser will now refresh automatically as you update your code

---

## 1. 🧱 Navbar - HTML Setup

### `index.html`
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Portfolio</title>
    <link rel="stylesheet" href="style.css">
</head>
<body>
    <div id="navbar-container">
        <div id="navbar">
            <div id="nameplate">
                <img src="assets/headshot.jpeg" id="small-headshot">
                <p>Jerry Chalamet</p>
    
            </div>
    
            <div id="pages">
                <p>About</p>
                <p>Experience</p>
                <p>Resume</p>
                <a href="https://www.linkedin.com/in/jasontenczar/">
                    <img src="assets/linkedin.png" alt="LinkedIn" />
                </a>
            </div>
        </div>
    </div>
```

✅ This sets up the layout structure.  
🧠 Think of each `div` like a labeled container that helps organize your webpage.

---

## 2. 🎨 Navbar - CSS Styling

### At the top of `style.css`
```css
@import url('https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100..900;1,100..900&display=swap');
```

### Global Styles
```css
body {
    font-family: 'Roboto', sans-serif;
    background-color: #FAFAFA;
    margin: 0;
    padding: 0;
}
```

### Typography (copy and paste from figma)
```css
h1 { 
    color: #161616;
    font-family: Roboto;
    font-size: 80px;
    font-style: normal;
    font-weight: 600;
    line-height: normal;
}

h2{
    color: #161616;
    font-family: Roboto;
    font-size: 40px;
    font-style: normal;
    font-weight: 600;
    line-height: normal;
}

p{
    color: #161616;
    font-family: Roboto;
    font-size: 18px;
    font-style: normal;
    font-weight: 400;
    line-height: normal;
}
```

### Navbar container and layout using figma as a guideline
```css
/* added in */
#navbar-container{
    display: flex;
    justify-content: center;
    align-items: center;
}

#navbar{
    margin-top: 10px;
    border-radius: 40px;
    display: flex;
    justify-content: space-between;
    align-items: center;
    flex-direction: row;
    width: 80%;
    padding-left: 6px;
    padding-right: 14px;
    box-sizing: border-box;
    box-shadow: 0px 8px 30px rgba(0, 0, 0, 0.2); /* smooth shadow */
}
```

### Small headshot, nameplate, and pages sections
```css
#small-headshot{
    /* from figma */
    width: 52px;
    height: 52px;
    aspect-ratio: 1/1;
    border-radius: 26px;
    /* added */
    object-fit: cover;
}

#nameplate{
    /* from figma */
    display: flex;
    align-items: center;
    gap: 10px;
    /* added */
    flex-direction: row;
    justify-content: center;
}

#pages{
    /* from figma */
    display: flex;
    align-items: center;
    gap: 50px;
}
```

---

## 3. 🚀 Hero Section

### Add this HTML
```html
    <div id="hero">
        <div id="hero-text">
            <h1>Jerry Chalamet</h1>
            <p>Software Engineer from San Francisco, California with experience in Frontend & Backend technologies.
                Pursuing a Master’s degree in Computer Science at the University of Florida.
            </p>
        </div>
        <div id="hero-image">
            <img src="assets/headshot.jpeg" alt="headshot">
        </div>
    </div>
```

### CSS styling (copy and paste from figma, added notes included)
```css
/* hero section */
#hero {
    /* from figma: */
    width: 100%;
    display: inline-flex;
    align-items: center;
    /* added in */
    justify-content: center;
    gap: 87px;
    margin-top: 100px;
}

#hero-text {
    /* from figma */
    display: flex;
    width: 553px;
    flex-direction: column;
    align-items: flex-start;
    gap: 60px;
}

#hero-image img{
    width: 400px;
    height: 400px;
    border-radius: 20px;
    box-shadow: 0px 275px 77px 0px rgba(0, 0, 0, 0.00), 0px 176px 70px 0px rgba(0, 0, 0, 0.01), 0px 44px 44px 0px rgba(0, 0, 0, 0.09), 0px 11px 24px 0px rgba(0, 0, 0, 0.10);
    /* added in */
    object-fit: cover;
}
```

---

## 4. 🧩 Cards Section

### HTML for card section
```html
<!-- now we will transition into using css classes instead of ids, a little more complex but more useful -->

<div id="experiences">
    <div class="card">
        <div class="card-text">
            <div class="card-body">
                <div class="card-company">
                    <img class="card-logo" src="assets/google.png" alt="">
                    <h2>Google</h2>
                </div>
                <p>Interned during the Summer of 2023 in Mountain View, California. </p>
            </div>
            <p>Software Developer</p>
        </div>
        <div>
            <img class="card-image" src="assets/google-hq.jpeg" alt="">
        </div>
    </div>

    <!-- duplicate this to create a second card -->
    <div class="card">
        <div class="card-text">
            <div class="card-body">
                <div class="card-company">
                    <img class="card-logo" src="assets/apple.png" alt="">
                    <h2>Apple</h2>
                </div>
                <p>Interned during the Summer of 2024 in Cupertino, California. </p>
            </div>
            <p>Software Developer</p>
        </div>
        <div>
            <img class="card-image" src="assets/apple-hq.jpeg" alt="">
        </div>
    </div>
</div>
```

### CSS for cards section
```css
#experiences{
    /* figma */
    display: flex;
    flex-direction: column;
    gap: 103px; 
    /* added */
    width: 100%;
    margin-top: 100px;
    align-items: center;
    justify-content: center;
}

.card{
    /* figma */
    display: flex;
    height: 392px;
    padding: 25px 26px 25px 61px;
    align-items: center;
    gap: 106px;
    border-radius: 40px;
    background: #FAFAFA;
    box-shadow: 0px 715px 200px 0px rgba(0, 0, 0, 0.00), 0px 458px 183px 0px rgba(0, 0, 0, 0.01), 0px 257px 154px 0px rgba(0, 0, 0, 0.05), 0px 29px 63px 0px rgba(0, 0, 0, 0.10);
    /* added */
    width: 80%;
    margin: auto;
}

.card-text{
    /* figma */
    display: flex;
    width: 336px;
    height: 275px;
    flex-direction: column;
    justify-content: space-between;
    align-items: flex-start;
}

.card-body{
    /* figma */
    display: flex;
    flex-direction: column;
    align-items: flex-start;
    gap: 22px;
    align-self: stretch;
}

.card-company{
    /* figma */
    display: flex;
    align-items: center;
    gap: 11px;
}

.card-logo{
    /* figma */
    width: 49px;
    height: 49px;
    aspect-ratio: 1/1;
    /* added */
    object-fit: cover;
}

.card-image{
    /* from figma */
    width: 511px;
    height: 341px;
    aspect-ratio: 511/341;
    border-radius: 20px;
}
```

---

## 5. 👣 Footer Section

### HTML
```html
<div id="footer">
    <p>👋 Hello there</p>
</div>
```

### CSS
```css
#footer{
    margin-top: 100px;
    display: flex;
    align-items: center;
    justify-content: center;
}
```
