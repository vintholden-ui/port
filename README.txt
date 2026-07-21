HOW THIS SITE WORKS
====================

Plain HTML/CSS — no coding tools, no build step. Double-click index.html
to open it straight in your browser and see the live layout.

FILES
-----
index.html                     → the work grid (homepage)
about.html                     → the about page
style.css                      → ALL styling lives here (colors, fonts, spacing)
fonts/                         → put your Gloucester MT font file in here
images/thrillberta/            → every image/video for Thrillberta lives here
images/fanduel-halftime-casino/ → same idea, one folder per project
images/...                     → one folder per project, matching the grid
projects/thrillberta.html      → the actual project page
projects/project-template.html → copy this whenever you start a NEW project

Right now every folder has solid black placeholder images so you can see
the layout working. Replace them with your real work — see below.


ADDING / SWAPPING IMAGES (per project, no more mix-ups)
-----------------------------------------------------------
Each project has its own folder under images/, so editing Thrillberta's
photos will never touch FanDuel's, Adrift Skate's, or anyone else's.

1. Open the folder for the project you're working on, e.g.
   images/thrillberta/
2. Drag your image or video files straight in. Name them anything —
   01.jpg, 02.jpg, hero-shot.jpg, whatever's clear to you.
3. Open that project's page in projects/ (e.g. projects/thrillberta.html)
   in a text editor.
4. Find the <div class="media-frame"> blocks — each one holds one
   image. Change the src="../images/thrillberta/01.jpg" filename to
   match what you actually dropped in.
5. To add MORE images than are currently there, copy a whole block:

     <div class="media-frame">
       <img src="../images/thrillberta/05.jpg" alt="describe it">
     </div>

   and paste it where you want it in the sequence. Order in the file
   = order on the page, top to bottom.

For a video, use this instead of the <img> line:
   <video src="../images/thrillberta/05.mp4" controls></video>

THE COVER IMAGE (shown in the homepage grid) is just another file in
that same project folder — by default named cover.jpg. Swap that one
file and the grid updates automatically.


WHY VERTICAL IMAGES USED TO TAKE UP THE WHOLE SCREEN — FIXED
------------------------------------------------------------------
Before, every image was set to fill the full width of the page, so a
tall portrait photo would end up enormous. Now every image sits inside
a "frame" that's capped at 78% of the screen's height — landscape
images fill the width like before (just slightly reined in), and
portrait images now stop comfortably short of a full page instead of
requiring several scrolls. Both are centered automatically. You don't
need to do anything for this — it's baked into style.css.


ADDING A BRAND NEW PROJECT (a 9th, 10th, etc.)
---------------------------------------------------
1. Make a new folder in images/, e.g. images/my-new-project/
2. Add a cover.jpg plus whatever else you need into it
3. Copy projects/project-template.html and rename the copy, e.g.
   projects/my-new-project.html
4. In that new file, replace "your-project-folder-name" everywhere
   with "my-new-project", and change the title/client/year text
5. In index.html, copy one whole <a class="work-tile">...</a> block,
   point its href at projects/my-new-project.html and its <img> at
   images/my-new-project/cover.jpg, and update the title/tag text


THE WORDMARK FONT — Gloucester MT Extra Condensed
-----------------------------------------------------
This one's a licensed Monotype font, not something available on free
font sites like Google Fonts — so it can't just be linked in the way
the body font is. But it very likely already lives on your own
computer, since it ships with Microsoft Office:

  On a Mac: open Font Book (Cmd+Space, type "Font Book"), search
  "Gloucester", right-click the result, and choose "Export". Save it
  as a .ttf or .otf file.

  On Windows: open Control Panel > Fonts, find Gloucester MT Extra
  Condensed, and copy the file (it's usually already sitting in
  C:\Windows\Fonts).

Once you have the file, rename it to exactly:
  GloucesterMTExtraCondensed.ttf   (or .otf, or .woff2 — any of these work)
and drop it into the fonts/ folder in this project. The site is
already wired to look for it there — nothing else to change, just
refresh the page.

If you don't add the file, the wordmark falls back to a plain
condensed serif that's a reasonable stand-in, so the site still looks
fine either way.


HOW TO PUT IT ON THE INTERNET FOR FREE
-----------------------------------------
Easiest option — Netlify Drop:

1. Go to https://app.netlify.com/drop
2. Drag this whole "portfolio" folder into the browser window
3. Netlify gives you a live URL in about 10 seconds
4. Make a free account when it prompts you, to keep the site
   permanently and optionally connect a real domain name later

Alternative — GitHub Pages: make a free GitHub account, create a
repository, upload these files, then turn on "Pages" in the repo
settings. You'll get a URL like yourname.github.io.

Either way, nothing here needs a paid host or any code beyond what's
already in this folder.
