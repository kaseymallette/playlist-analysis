# playlist-analysis

## Purpose

This project explores whether songs curated to express a morally assertive or judgment-oriented stance share measurable audio and popularity characteristics. Using a human-curated Spotify playlist as a labeled dataset, the analysis examines relationships between audio features (e.g., valence, energy, acousticness, loudness) and track popularity to identify clustering patterns that may reflect emotional stance, intensity, or social reception.

The goal is not to infer lyrical meaning directly, but to test whether audio structure alone carries signals associated with morally charged expression. Lyrics analysis is considered future work.

## Feature Selection 

Valence, energy, and acousticness capture complementary dimensions of musical expression that are central to how assertiveness is conveyed.

- **Valence** measures emotional positivity (low = negative or unresolved, high = positive or triumphant).
- **Energy** measures intensity and forcefulness (low = subdued, high = forceful or driving).
- **Acousticness** measures how stripped-down versus produced a track is (high = intimate or sincere, low = confrontational or performative).

These dimensions are analyzed together because they describe *how* a message is delivered, not *what* it says.

In this playlist, valence and energy are weakly correlated, indicating that morally assertive or judgment-oriented expression can manifest through multiple emotional modes. Valence is also weakly correlated with acousticness, suggesting that emotional positivity varies independently from production style. Acousticness further differentiates whether assertiveness is expressed through introspection, confrontation, or unresolved emotional tension.

### Expressive Clusters (KMeans on Energy, Valence, Acousticness)

**Cluster 0: Direct moral affirmation or self-assertion**  
High energy, high valence, low acoustic
*(direct delivery + emotionally positive affect)*

**Cluster 1: Reflective moral certainty**  
Moderate energy, lower valence, high acoustic
*(reflective delivery + sober, introspective affect)*

**Cluster 2: Direct moral opposition or critique**  
High energy, low valence, low acoustic 
*(direct delivery + emotionally negative affect)*

**Cluster 3: Unresolved moral unease**  
Moderate energy, very low valence, low acoustic
*(restrained delivery + emotionally unresolved affect)*


