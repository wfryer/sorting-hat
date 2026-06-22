# ⚡ Sorting Hat Ceremony

An interactive, theatrical Hogwarts Sorting Hat experience for classroom use. Designed for teachers running group activities, summer camps, and team-building events. The animated sorting hat deliberates, the house is announced with drama, and a live scoreboard fills in as each student is sorted.

**[Try the live demo →](https://wfryer.github.io/sorting-hat/)**

---

## Features

- **Animated sorting hat** that shakes and wobbles while "deliberating," with golden eyes that light up during the suspense
- **Dramatic house reveal** with crest image, house name flyout, and a full-screen color flash in house colors
- **Live scoreboard** that accumulates sorted students under their house banner in real time
- **Supports 1 to 4 houses**: toggle any of the four Hogwarts houses on or off before sorting begins
- **Balanced random assignment**: students are distributed evenly across selected houses, in random order
- **House crest images** loaded from Wikimedia Commons, with built-in SVG heraldic shield fallbacks if images are unavailable
- **Embedded music player** linking to HP classroom ambience on YouTube
- **Final results screen** with celebration sparkles and a print option
- **Single HTML file**: no build tools, no dependencies, works in any browser

---

## How to Use

### Setup (takes about 30 seconds)

1. Open `sorting-hat.html` in a browser and project it on a screen
2. Optionally click **Play Music** to start the background ambience
3. Check or uncheck houses (all four are selected by default)
4. Type student first names in the text box, one per line
5. Click **Begin the Sorting Ceremony**

### The Ceremony

For each student:

1. The student's name appears on screen in large gold text
2. Click **Place the Hat** to begin the deliberation
3. The hat shakes for about 2.5 seconds while the golden eyes glow
4. A speech bubble announces the house
5. The house crest and name fly in dramatically
6. The student's name slides into the scoreboard under their house
7. Click **Next Student** to continue

When everyone has been sorted, the final roster appears with house totals and a sparkle celebration. Use the **Print Results** button to print or save as PDF.

---

## Customization

### Change the music

Open `sorting-hat.html` in a text editor. Find this line near the top of the `<body>`:

```html
<iframe id="music-iframe" src="" data-src="https://www.youtube.com/embed/uYZKQN3a4Sg?autoplay=1&start=0"
```

Replace the video ID (`uYZKQN3a4Sg`) with any YouTube video ID you prefer. Hedwig's Theme, the full HP soundtrack, or any ambient music works well. The video plays muted-to-unmuted only after the teacher clicks the Play Music button, which satisfies browser autoplay rules.

### Swap in verified house crest images

Near the top of the `<script>` block, each house definition has a `crestUrl` property:

```javascript
const HOUSES = {
  gryffindor: {
    ...
    crestUrl: 'https://upload.wikimedia.org/wikipedia/commons/...',
  },
  ...
};
```

If the default Wikimedia URLs do not load in your environment, replace them with any direct image URL (PNG or SVG). The app always falls back to built-in SVG heraldic shields if an image fails to load, so sorting works regardless.

### Change colors, fonts, or house names

All visual tokens are CSS custom properties in the `:root` block at the top of the `<style>` section. House names, animals, and glow colors are in the `HOUSES` JavaScript object.

---

## Deployment to GitHub Pages

1. Create a new GitHub repository (for example, `sorting-hat`)
2. Upload `sorting-hat.html` and rename it to `index.html`
3. Go to **Settings > Pages**
4. Under **Branch**, select `main` and `/ (root)`, then click **Save**
5. Your app will be live at `https://yourusername.github.io/sorting-hat/` within a minute or two

The app has no server requirements, no build step, and no external JavaScript libraries. It runs entirely in the browser from a single file.

---

## Project Structure

```
sorting-hat/
  index.html    The complete app (HTML, CSS, and JS in one file)
  README.md     This file
```

---

## Background and Credits

Built for use in Dr. Wes Fryer's **Wizarding Minecraft Build Camp** (Summer 2026, AstroKids Club, Providence Day School). Designed to run on a classroom projector for groups of 6 to 30 students.

- Sorting hat SVG illustration: original, built into the HTML
- House crest images: Wikimedia Commons (with SVG fallback)
- Background music: Hogwarts Classroom Ambience via YouTube
- Starfield background: canvas-based animation, no libraries

HP, Hogwarts, and all related names are trademarks of Warner Bros. Entertainment Inc. This project is an unofficial, non-commercial educational tool.

---

## License

MIT License. Free to use, adapt, and share with attribution.

Made with ⚡ by [Wes Fryer](https://wesfryer.com) | [AstroKids Club](https://astrokidsclub.org)
