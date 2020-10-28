<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <link
      href="https://fonts.googleapis.com/css2?family=Roboto:wght@300&display=swap"
      rel="stylesheet"
    />
    <link href="https://www.cssscript.com/demo/sticky.css" rel="stylesheet" type="text/css">
    <link rel="stylesheet" href="style.css" />
    <link rel="stylesheet" href="menu.css" />
    <title>Hamburger Overlay Navigation Drawer Example</title>
    <style>
    .menu-wrap {
  position: fixed;
  top: 0;
  left: 0;
  z-index: 1;
}
.menu-wrap .toggler {
  position: absolute;
  top: 0;
  left: 0;
  opacity: 0;
  height: 50px;
  width: 50px;
  cursor: pointer;
  z-index: 2;
}
.menu-wrap .hamburger {
  position: absolute;
  top: 0;
  left: 0;
  height: 60px;
  width: 60px;
  background: transparent;
  padding: 1rem;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  z-index: 1;
}

/* Hamburger line */
.menu-wrap .hamburger > div {
  position: relative;
  top: 0;
  left: 0;
  width: 100%;
  height: 2px;
  background: #fafafa;
  flex: none;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: 0.4s;
}

/* Hamburger top & bottom line */
.menu-wrap .hamburger > div:before,
.menu-wrap .hamburger > div:after {
  content: "";
  position: absolute;
  top: 10px;
  left: 0;
  background: inherit;
  height: 2px;
  width: 100%;
  z-index: 1;
}
.menu-wrap .hamburger > div:after {
  top: -10px;
}

/* Toggler Animation */
.menu-wrap .toggler:checked + .hamburger > div {
  transform: rotate(135deg);
}
.menu-wrap .toggler:checked + .hamburger > div:before,
.menu-wrap .toggler:checked + .hamburger > div:after {
  top: 0;
  transform: rotate(90deg);
}

/* Rotate on hover when checked */
.menu-wrap .toggler:checked:hover + .hamburger > div {
  transform: rotate(225deg);
}
.menu {
  position: fixed;
  top: 0;
  left: 0;
  background: rgb(77, 58, 58, 0.8);
  height: 100vh;
  width: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  opacity: 0;
  transition: all var(--menu-speed) ease;
}
.menu > div {
  position: relative;
  top: 0;
  left: 0;
  height: 100%;
  width: 100%;
  flex: none;
  display: flex;
  align-items: center;
  justify-content: center;
  text-align: center;
  opacity: 0;
  transition: opacity 0.4s ease-in;
}
.menu ul {
  list-style: none;
}
.menu li {
  padding: 1rem 0;
}
.menu > div a {
  text-decoration: none;
  color: #fafafa;
  font-size: 1.5rem;
  opacity: 0;
  transition: opacity 1s ease-in;
}
.menu a:hover {
  color: rgb(230, 177, 177);
  transition: color 0.3s ease-in;
}

/* Show Menu */
.menu-wrap .toggler:checked ~ .menu {
  opacity: 1;
  width: 30vw;
  transition: all var(--menu-speed) ease;
}
.menu-wrap .toggler:checked ~ .menu > div {
  opacity: 1;
  transition: opacity 0.4s ease-in;
}
.menu-wrap .toggler:checked ~ .menu > div a {
  opacity: 1;
  transition: opacity 1s ease-in;
}

@media (max-width: 500px) {
  header {
    background: url("./bg-img.jpg") no-repeat 40% center / cover;
  }
  .menu-wrap .toggler:checked ~ .menu {
    width: 65vw;
  }
}
* {
  padding: 0;
  margin: 0;
  box-sizing: border-box;
}
:root {
  --menu-speed: 0.75s;
}
body {
  font-family: "Roboto";
  line-height: 1.4;
  background: url("https://source.unsplash.com/WoZgy7ZwgBI/1920x1080") no-repeat center center/cover;
   height: 100vh;
  width: 100vw;
  overflow: hidden;
}
main {
  margin: 150px auto;
  max-width: 728px;
  padding: 2rem;
  background-color: #fafafa;
  border-radius: 3px;
  text-align: center;
}

    </style>
  </head>
  <body>
    <div class="menu-wrap">
      <input type="checkbox" class="toggler" />
      <div class="hamburger"><div></div></div>
      <div class="menu">
        <div>
          <ul>
            <li><a href="#">Home</a></li>
            <li><a href="#">CSS</a></li>
            <li><a href="#">Script</a></li>
            <li><a href="#">Com</a></li>
          </ul>
        </div>
      </div>
    </div>
