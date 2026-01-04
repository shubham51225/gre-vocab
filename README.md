Access here: https://shubham51225.github.io/gre-vocab/

# GRE Vocabulary App

A progressive web app for mastering GRE vocabulary using an intelligent adaptive algorithm that automatically tracks your performance and prioritizes words you struggle with—no manual self-rating required.

## The Problem with Traditional Flashcards

Most spaced repetition apps ask you to rate how well you know a word after seeing it. The problem? When you're looking at a word and its definition, it *always* feels familiar. You think "yeah, I know this one" and rate it as easy—only to blank on it during the actual test. This self-assessment bias undermines the entire learning process.

## Adaptive Retention Algorithm (ARA)

This app takes a different approach. Instead of asking you to judge your own knowledge, it watches how you actually perform in quizzes and automatically adjusts which words need more attention.

Every word has a "heat" score from 0 to 100. Hot words are ones you're struggling with. The algorithm calculates heat based on your real quiz performance:

**Heat increases when:**
- You answer incorrectly (+15 heat per wrong answer)
- You recently got it wrong and haven't recovered
- Your overall accuracy for that word is low

**Heat decreases when:**
- You answer correctly (builds a streak)
- You maintain high accuracy over multiple attempts
- Time passes without mistakes

Words with heat above 30 are considered "hot" and appear in the dedicated Hot Words review section. Once you achieve mastery—5 consecutive correct answers with 80%+ overall accuracy across at least 3 attempts—the word cools down and exits the hot list.

## How to Use

The app follows a simple daily workflow:

**Learn New Words** takes you through vocabulary you haven't seen yet. Words are randomly shuffled each day, but the shuffle stays consistent throughout the day so you can take breaks and pick up where you left off. Tap the card to flip it, read the definition and examples, then tap Next to mark it as learned and move on.

**Take Quiz** tests you on words you've already learned. Questions alternate between showing a definition (pick the word) and showing a word (pick the definition). Your answers are automatically tracked—no need to self-assess. The app remembers what you got right and wrong.

**Review Hot Words** appears when you have struggling words. This quiz focuses specifically on words where your performance has been weak. Keep reviewing until words cool down through consistent correct answers.

## Understanding the Interface

The home screen shows three key numbers: how many words you've learned, how many "hot" words need attention, and your current streak. The progress ring visualizes your overall completion percentage.

In the Browse section, you can search for any word and filter by status. The heat indicator on each word shows its current difficulty level for you personally. Tapping a word reveals full details including your performance statistics.

The Stats view shows your weekly activity calendar and lists your hottest words ranked by how much they need review.

The app works with any number of words. Economics examples are optional and can be toggled off in settings if you prefer general-purpose vocabulary study.

## Themes

Three visual themes are available in Settings:

**Light** provides a clean, minimal interface with maximum readability for daytime use.

**Dark** offers a true black background optimized for OLED screens and nighttime study sessions.

**Shubham's Theme** is a cyberpunk-inspired aesthetic featuring deep purple backgrounds, neon pink and cyan accents, and ambient glow effects. This theme is set as the default.

## Technical Details

The app is a single HTML file with no external dependencies. It works offline once loaded and stores all progress in your browser's localStorage. Data persists across sessions but is tied to your browser—clearing browser data will reset your progress.

You can export your progress as a JSON file from Settings at any time. This backup includes all learned words, performance data, and settings. Import this file on another device or after clearing your browser to restore your progress.

## Algorithm Details

The heat calculation considers multiple factors:

```
Base heat: 50 (neutral starting point)
+ Wrong answers × 15
- Correct streak × 10
- Overall accuracy × 30 (scaled)
+ Recent mistake bonus: 20 (if wrong within 24 hours)
+ Dormant struggle bonus: 10 (if >72 hours and more wrongs than rights)
```

Heat is clamped between 0 and 100. Words reaching mastery (5-streak, 80% accuracy, 3+ attempts) have their heat reset to 0.

The daily shuffle uses a seeded random algorithm based on the current date. This means if you study at 9am and return at 9pm, you'll continue from where you stopped rather than seeing a completely new random order. The shuffle resets at midnight.

## Privacy

All data stays on your device. The app makes no network requests after initial load and collects no analytics. Your vocabulary progress exists only in your browser's localStorage.

---

Built for focused GRE preparation. No accounts, no subscriptions, no distractions—just you and the words.

## Contributing

This is a single-file application, so contributing is straightforward. Fork the repository, edit `index.html`, and submit a pull request. The entire app — HTML, CSS, JavaScript, and all 5,867 vocabulary entries — lives in that one file.


