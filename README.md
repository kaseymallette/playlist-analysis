# playlist-analysis

## Purpose

This project explores whether songs curated to express a morally assertive or judgment-oriented stance share measurable audio and popularity characteristics. Using a human-curated Spotify playlist as a labeled dataset, the analysis examines relationships between audio features (e.g., valence, energy, acousticness, loudness) and track popularity to identify clustering patterns that may reflect emotional stance, intensity, or social reception.

The goal is not to infer lyrical meaning directly, but to test whether audio structure alone carries signals associated with morally charged expression. Lyrics analysis is considered future work.

## Why Valence and Energy Matter

Valence and energy capture two orthogonal dimensions of musical expression that are central to how assertiveness is conveyed.

- **Valence** measures emotional positivity (low = negative or unresolved, high = positive or triumphant).
- **Energy** measures intensity and forcefulness (low = subdued, high = aggressive or driving).

These dimensions are analyzed together because they describe *how* a message is delivered, not *what* it says.

In this playlist, valence and energy are weakly correlated, indicating that morally assertive or judgment-oriented expression can manifest through multiple emotional modes:

- **High energy, low valence** — anger, grievance, moral criticism  
- **High energy, high valence** — confidence, certainty, triumph  

This separation allows the analysis to identify distinct expressive clusters without relying on lyrical interpretation.
