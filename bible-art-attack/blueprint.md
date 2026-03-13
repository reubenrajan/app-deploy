You are a web engineer.
Build a polished interactive web game called:

🔥 Bible Art Attack!! 🎨

The game is used in church/youth events where contestants generate AI images of Bible events in random art styles.
The application should be modern, playful, and visually engaging. Implement as a single page web application with inline css and js.
The design should feel like a fun game show.

------------------------------------------------
GAME FLOW
------------------------------------------------

1️⃣ Landing Page

Display a vibrant introduction screen with:

Title:
🔥 Bible Art Attack!! 🎨

Subtitle:
"Spin for a Bible Theme. Spin for an Art Style. Create an epic AI masterpiece!"

Show a **collage grid** of example theme/style combinations such as:
🌊 Red Sea Crossing — IMAX Epic Scene  
🦁 Daniel in the Lions' Den — Hyper-realistic  
🌈 Noah's Ark — Pixar-style  
⚔️ David vs Goliath — Comic Book Style  
🎄 Nativity — Disney Classic  
🔥 Burning Bush — LEGO Style  
🌍 Creation — Minecraft Style

Have the collage grid be visually appealing with actually images created with the theme/style combinations.

Each card should:
- have rounded corners
- image with the theme/style combination
- subtle hover animation
- scale slightly on hover
- soft shadow

Below the collage place a large:

"Start Game" button

------------------------------------------------
2️⃣ THEME SPINNER
------------------------------------------------

After clicking Start Game, show the game screen.

First step:
Spin for a Bible theme.

Themes list (25 total):

Creation of the World  
The Fall of Man  
Noah and the Ark  
Tower of Babel  
Abraham & Isaac  
Jacob Wrestling the Angel  
Joseph's Coat of Many Colors  
Burning Bush  
Red Sea Crossing  
Ten Commandments  
Walls of Jericho  
Gideon and the 300  
Samson at the Temple  
David and Goliath  
Elijah on Mount Carmel  
Daniel in the Lions' Den  
Jonah and the Great Fish  
Birth of Jesus  
Jesus Calms the Storm  
Feeding the 5,000  
Transfiguration  
Last Supper  
Crucifixion  
Resurrection  
Pentecost

Theme spinner behavior:

- Press "Spin"
- Wheel animates for ~2 seconds
- Random theme is selected
- Theme appears prominently

The random theme should be displayed within the wheel after spinning.

Example display:

📖 Theme Selected  
"Daniel in the Lions' Den"

------------------------------------------------
3️⃣ STYLE SPINNER
------------------------------------------------

After the theme is selected, enable the style spinner.

Styles list (7 total):

Hyper-realistic photography  
IMAX epic scene  
Pixar-style 3D animation  
Comic book superhero style  
Disney classic animation  
Minecraft-style block art  
LEGO-style characters  

Behavior:

- Press "Spin"
- Wheel spins
- Random style appears

The random style should be displayed within the wheel after spinning.

Example result:

🎨 Style Selected  
"Pixar-style 3D animation"

------------------------------------------------
4️⃣ COMPLETION SYSTEM
------------------------------------------------

After a style is used:

Press:
"Mark Style Completed"

That style should be removed from the available styles list.

Display remaining styles count.

Example:

Remaining Styles: 5

When all styles are used:
Trigger a celebration animation (confetti).

------------------------------------------------
5️⃣ GAME CONTROLS
------------------------------------------------

Buttons needed:

Spin
Mark Style Completed
Reset Game

Reset Game should:
- restore all styles
- reset themes
- return to theme spinner stage

------------------------------------------------
6️⃣ UI DESIGN
------------------------------------------------

Color palette:

Purple
Indigo
Gold
Soft pink highlights

Background:
Gradient playful background.

Spinner display:

Large circular animated element
with rotating animation using Framer Motion.

Cards should be soft, playful, and modern.

------------------------------------------------
7️⃣ COMPONENT STRUCTURE
------------------------------------------------

Structure the code cleanly:

/components
    LandingPage
    SpinnerWheel
    ThemeDisplay
    StyleDisplay
    StyleList
    ControlButtons

/pages
    Game

Use React hooks for state management.

------------------------------------------------
8️⃣ RESPONSIVENESS
------------------------------------------------

The UI should work on:

Desktop
Tablet
Projector display

Ensure:
Large readable text
Large buttons
Centered layout

------------------------------------------------
9️⃣ BONUS FEATURES (optional but preferred)

Add:

- subtle hover animations
- glow effect on selected theme
- glow effect on selected style
- confetti animation when styles run out
- small icons for themes
- smooth transitions between screens

------------------------------------------------
OUTPUT REQUIREMENTS
------------------------------------------------

Provide:

1️⃣ Full React component code
2️⃣ Clear separation of components
3️⃣ Tailwind styling
4️⃣ Clean readable code
5️⃣ Comments explaining key parts