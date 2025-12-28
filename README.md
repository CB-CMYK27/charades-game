# 🎭 Holiday Charades - Simple PWA Game

A single-phone charades game you can play at the pub. Pass it around, act things out, have a laugh.

## What You're Building Today

- A web app you install on your phone (like a real app!)
- AI generates charades topics (no more thinking of ideas)
- Keeps score automatically
- Remembers what's been used (no repeats)
- Everyone gets one skip per round
- Works offline once installed

## Quick Start (For Students)

### Step 1: Get the Code (2 minutes)

1. Go to the instructor's GitHub repo
2. Click the **Fork** button (top right)
3. You now have your own copy!

### Step 2: Deploy to Your Phone (3 minutes)

1. In YOUR forked repo, go to **Settings**
2. Click **Pages** (left sidebar)
3. Under "Source", select **main** branch
4. Click **Save**
5. Wait 1-2 minutes
6. Your app is live at: `https://YOUR-USERNAME.github.io/REPO-NAME/`

### Step 3: Install on Your Phone (2 minutes)

**iPhone:**
1. Open the URL in Safari
2. Tap the Share button
3. Scroll down → "Add to Home Screen"
4. Tap "Add"

**Android:**
1. Open the URL in Chrome
2. Tap menu (⋮)
3. Tap "Install app"

**You now have a working charades app!**

### Step 4: Connect to AI (taught together)

We'll do this together in the workshop:
1. Import the n8n workflow
2. Update your webhook URL
3. Test it
4. Topics now generate!

---

## How to Play

1. **Setup**: Add players (names + optional photos), set timer and rounds
2. **Play**: Pass phone to first player → they tap START → topic appears
3. **Act**: Player acts it out while timer runs
4. **Score**: 
   - If someone guessed it → tap "Got It!" → select who guessed → both get points
   - If nobody guessed → tap "Nobody Guessed" → no points
5. **Skip**: Each player can skip ONCE per round if they get something impossible
6. **Win**: Most points after all rounds wins!

---

## Customization Ideas (Afternoon Session)

### Easy Changes (in style.css)

**Change Colors:**
```css
/* Lines 8-15 - Change these! */
--primary: #FF3366;      /* Try #00D9FF for blue */
--secondary: #FFD93D;    /* Try #00FF88 for green */
--success: #6BCF7F;
```

**Change Fonts:**
```css
/* Line 20 */
--font-display: 'Righteous', cursive;  /* Try other Google Fonts */
```

### Medium Changes (in app.js)

**Add Your Own Fallback Topics:**
```javascript
// Lines 218-227 - Add your own!
const fallbacks = [
    { category: 'Movie', emoji: '🎬', topic: 'Your Favorite Movie' },
    // Add more here!
];
```

**Customize Timer Length Options:**
```javascript
// In HTML, lines 20-25
<option value="15">15 seconds</option>  /* Add fast mode! */
<option value="180">3 minutes</option>  /* Add slow mode! */
```

### Advanced Changes

**Modify AI Prompt (in n8n):**
- Make it generate funnier topics
- Add Scottish references
- Make it seasonal
- Add difficulty levels

**Add Sound Effects:**
```javascript
// Add this after line 334
const successSound = new Audio('success.mp3');
successSound.play();
```

---

## Files Explained

- `index.html` - The structure (what's on the page)
- `style.css` - The look (colors, fonts, layout)
- `app.js` - The logic (what happens when you click)
- `manifest.json` - PWA config (makes it installable)
- `service-worker.js` - Offline support (caches the app)
- `n8n-workflow.json` - AI workflow (import this into n8n)

---

## Troubleshooting

**App won't install on phone:**
- Make sure you're using HTTPS (GitHub Pages does this automatically)
- Try a different browser (Safari on iOS, Chrome on Android)
- Check icons exist (they're optional but help)

**AI not generating topics:**
- Check your n8n webhook URL is correct in `app.js` line 8
- Make sure n8n workflow is active (toggle top-right)
- Use fallback topics (they work without AI)

**Photos not working:**
- Camera API requires HTTPS (you have this via GitHub Pages)
- Grant camera permission when asked
- Photos are optional anyway!

**Game stuck:**
- Refresh the page
- Check browser console for errors (F12)
- Ask for help!

---

## What You Learned Today

1. **PWAs**: Web apps that install like native apps
2. **GitHub Pages**: Free hosting for static sites
3. **n8n**: Visual automation/backend tool
4. **Claude API**: Using AI to generate content
5. **State Management**: Keeping track of game data
6. **Camera API**: Taking photos in the browser

---

## Ideas to Make it Your Own

Want to customize this game and make it unique? Here are tons of ideas to inspire your own build! Pick what sounds fun to you.

### 🎭 Gameplay Variations

**Difficulty Levels**
- Easy/Medium/Hard topics with point multipliers (2x for hard topics!)
- "Impossible Mode" - super obscure topics for brave players
- Dynamic difficulty that adjusts based on player performance

**Special Round Types**
- **Sound Effects Only** - No hand gestures allowed
- **Emoji Round** - Act it out using only emojis shown on screen
- **Speed Round** - 30 seconds, rapid-fire topics (2x points)
- **Team Mode** - Split into teams, combine scores
- **Reverse Charades** - Everyone acts, one person guesses
- **One Word Hints** - Guesser can ask for a hint (costs points)

**Challenges & Power-ups**
- Random challenges mid-game: "Act with one hand behind your back"
- "Steal" - Guess another player's topic for bonus points
- "Double or Nothing" - Risk your points on a harder topic
- "Swap" - Trade your topic with the next player
- "Freeze" - Skip your turn but keep your skip available

### 🎨 Visual & Audio Features

**Animations & Effects**
- Confetti explosion when someone scores
- Player avatars that "dance" when they score
- Dramatic countdown with sound effects (tick-tick-tick-BUZZ!)
- Victory animations for the winner
- Shake animation when time's running out

**Photo Features**
- **Reaction Photos** - Snap a photo of the guesser's face when they get it
- **Action Shots** - Auto-capture during the performance
- **Photo Gallery** - End-of-game slideshow of all the chaos
- Silly filters/overlays for player photos (hats, glasses, etc.)
- Polaroid-style photo frames with timestamps

**Sound Design**
- Background music (toggle on/off)
- Timer ticking sound that speeds up
- Buzzer sound for time running out
- Cheering/applause sounds for correct guesses
- Funny sound effects for skips

### 📊 Stats & Achievements

**Player Stats**
- Best winning streak
- Fastest correct guess (track time to completion)
- "Most skips used" (hall of shame)
- "Hardest topic conquered"
- Total games played/won across sessions

**Achievements/Badges**
- "Hat Trick" - 3 correct in a row
- "Comeback Kid" - Win from last place
- "Perfect Round" - No skips used
- "Speed Demon" - Guessed in under 10 seconds
- "Champion" - Win 5 games in a row
- "Unbreakable" - Never skip in a whole game

**Lifetime Progress**
- Track stats across multiple games (using localStorage)
- Player profiles with win rates and favorite categories
- Global leaderboard (if you add a simple backend like Firebase)
- "Season" tracking (weekly/monthly resets)

### 🎲 Content Variations

**Topic Categories**
- Let players choose categories: Movies, Songs, Actions, Famous People, Objects
- "Wild Card" - Random category mix each turn
- Custom word lists (upload your own topics via CSV)
- Player-submitted topics (add your own during setup)

**AI-Enhanced Topics**
- **Difficulty ratings** from AI (show stars before revealing)
- **Topic hints** - Get a one-word hint from the AI (costs points)
- **Related word chains** - Each topic builds on the last
- **Inside jokes** - AI learns your group's interests over time
- **Themed generators** - "Generate topics about our friend group"

**Themed Packs**
- Holiday-specific (Halloween, Christmas, New Year's, Easter)
- Decade themes (60s, 70s, 80s, 90s, 2000s)
- Genre packs (Horror movies, Sports, Video games, TV shows)
- Location-based (Scottish culture, Local landmarks, Inside jokes)
- Age-appropriate packs (Kids mode, Adult mode)

### 🎪 Social & Sharing Features

**Sharing**
- Share final scores to social media with game highlights
- Generate a "highlight reel" text summary ("Sarah guessed 8 topics!")
- QR code to invite friends to join next game
- Screenshot the leaderboard with player photos
- "Best moment" voting at the end

**Replay Value**
- "Rematch" button with same players/settings
- "Revenge Mode" - Loser picks next theme
- Save favorite topics to replay later
- "Challenge a Friend" - Send them your hardest topic
- Tournament mode - Track winners across multiple games

### 🛠️ Technical Challenges

**Multi-Device Mode** (more ambitious!)
- Host device + player devices
- Players buzz in from their own phones
- Everyone sees the topic simultaneously
- Real-time score updates across all devices

**Voice Features**
- Voice-activated scoring: say "Got it!" to trigger the button
- Voice recordings of the acting (playback at the end)
- Speech-to-text for topic hints

**Advanced Camera Features**
- Use phone camera to detect gestures (AI motion tracking)
- AR overlays during acting (funny hats, effects)
- Motion tracking to score "effort level"
- GIF creation from the performance

**Accessibility**
- Large text mode for visibility
- Color blind friendly themes
- Screen reader support
- Haptic feedback (vibrations) for timer warnings

### 🎯 Quick Win Ideas (Start Here!)

If you're not sure where to start, these are fun and relatively easy:

1. **Change the theme colors** - Make it match your favorite sports team
2. **Add custom fallback topics** - Inside jokes about your friend group
3. **Create themed packs** - 80s movies, your hometown, your school
4. **Add confetti** - Use a library like canvas-confetti for celebrations
5. **Add sound effects** - Free sounds from freesound.org
6. **Achievement badges** - Simple icons that show up when you do something cool
7. **Best of 3 mode** - Play multiple games and track overall winner

### 🚀 Advanced Ideas (For the Bold!)

- **Firebase integration** - Real leaderboard across all players worldwide
- **Twitch integration** - Stream your game and let chat vote
- **TikTok mode** - Auto-record and upload performances
- **AI judge** - Use computer vision to rate your acting
- **Betting system** - Wager points on other players
- **Mini-games** - Bonus rounds between regular rounds

---

**Share your version!**

Built something cool? Share it with the community! Fork this repo, make it your own, and show us what you created. The best ideas might get featured here.

Tag your builds with `#CharadesPWA` and let's see what everyone comes up with!

---

## Credits

Built at AI Builders Buildathon  
Dundee Founders Collective  
December 2025

---

## License

MIT License - Do whatever you want with it!
