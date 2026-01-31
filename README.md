# playlist-analysis

## Introduction 

This project analyzes the measurable audio characteristics of songs curated for a moral judgment–themed playlist. The playlist was curated by the author to reflect a range of perceived moral postures, spanning from morally superior, judgment-driven stances to morally and emotionally exhausted ones. While the songs are not assumed to make explicit moral claims, they are interpreted as responding to perceived wrongdoing with varying degrees of moral certainty, agency, and exhaustion. 

## Methods 

The dataset consists of 75 songs curated by the author into a moral judgment–themed playlist. Audio features were extracted using a Spotify playlist exporter service and saved as a CSV file. In addition to audio features, Spotify popularity scores, album release year, and genre metadata were retrieved to support descriptive analysis.

As an exploratory analysis, songs were examined using Spotify audio features, with particular focus on energy and valence, to assess whether songs associated with different perceived moral postures clustered differently. 
- **Valence** reflects the emotional orientation of a song, ranging from darker, unresolved, or tense states to lighter, more resolved or affirming ones.
- **Energy** captures how forcefully a song presents itself, from low-intensity and restrained to high-intensity and driving.

It was hypothesized that songs representing moral judgment would tend toward lower valence, reflecting negative appraisals of harm or wrongdoing, while differences in energy would emerge depending on how forcefully or intensely the moral judgment was expressed.

To identify an appropriate number of clusters, k-means clustering was performed across a range of k values and evaluated using silhouette score. To support interpretation of the resulting clusters, the most popular songs within each cluster were examined qualitatively by reviewing their lyrics. This step was used to assess whether the clusters aligned with the perceived moral postures that motivated the original playlist curation.

## Results

### Popularity Distribution

Figure 1 illustrates the popularity distribution of songs included in the moral judgment–themed playlist. The playlist spans a wide range of popularity values, including both relatively obscure tracks and highly popular songs, demonstrating that the dataset includes both niche and mainstream music.

![Popularity Distribution](images/popularity_distribution.png)

### Decade Distribution

Figure 2 shows the distribution of album release decades for songs in the playlist. The majority of tracks originate from the 2010s and 2020s, indicating that the playlist is predominantly composed of contemporary music.

![Decade Distribution](images/decade_distribution.png)

### Genre Distribution

Figure 3 examines the distribution of genre labels for songs in the playlist. Spotify genre metadata is not consistently provided at the track level, resulting in missing genre data. While the available labels span a wide range of genres, they are sparse and highly fragmented. As a result, genre-based analysis was not pursued further.

![Genre Distribution](images/genre_distribution.png)

### Valence vs. Energy

Figure 4 shows the distribution of songs plotted by valence and energy. Songs span a broad range of emotional orientation and intensity, with no clear linear relationship, suggesting potential structure suitable for clustering.

![Valence vs. Energy](images/valence_vs_energy.png)

### Cluster Selection 

Figure 5 presents silhouette scores for k-means clustering across a range of k values (2-8). Among the values tested, k = 6 yielded the highest silhouette score and was selected for subsequent analysis. 

![Cluster Selection](images/silhouette_by_k.png)

### Cluster Results

Figure 6 shows the results of k-means clustering applied to valence and energy (k = 6). The clusters occupy distinct regions of the valence–energy space, corresponding to different combinations of emotional orientation and intensity. Three of the six clusters are predominantly located above an energy value of 60, while the remaining clusters occupy mid-to-lower energy ranges.

![Cluster Results](images/cluster_results.png)

#### Cluster Characteristics

Table 1 summarizes the mean valence, mean energy, and number of songs for each cluster.

| Cluster | Mean Valence | Mean Energy | Song Count |
|---------|--------------|-------------|------------|
| 0       | 79.50        | 72.00       | 6          |
| 1       | 25.90        | 56.81       | 21         |
| 2       | 25.75        | 82.42       | 12         |
| 3       | 51.29        | 49.94       | 17         |
| 4       | 49.25        | 84.88       | 16         |
| 5       | 24.33        | 28.33       | 3          |


## Discussion

Although the clusters separate quantitatively by valence and energy, they also differ in how emotional and moral distress is expressed. The Discussion interprets these differences by examining representative lyrics from each cluster. To support interpretation, valence and energy were mapped onto moral–emotional states. In this framework, valence reflects how harm or injustice is appraised, while energy reflects how the narrator responds to that appraisal.

Valence is interpreted as follows: 
- **Low valence** = *Pessimism*, bleak expectations about change or repair
- **Medium valence** = *Woundedness*, acknowledgment of moral or relational injury
- **High valence** = *Outrage*, morally charged anger toward a perceived source of harm

Energy corresponds to a response posture: 
- **Low energy** = *Exhaustion*
- **Medium energy** = *Defensiveness*
- **High energy** = *Defiance* 

Together, these dimensions distinguish not only how negatively an experience is felt, but how that experience is managed. 

### Case 1: Clusters 1 and 2

Clusters 1 and 2 share low valence but differ in energy, ranging from medium to high. 
- Cluster 1 (n = 21; valence = 25.9; energy = 56.8) is characterized by low valence and moderate energy.
- Cluster 2 (n = 12; valence = 25.8; energy = 82.4) is characterized by low valence and high energy.

#### Cluster 1

Cluster 1 captures songs in which the narrator appears pessimistic and frustrated by societal and relational pressure. 

*“Way Down We Go”* by Kaleo (2016)

> They will run you down, down ’till you fall  
> And they will run you down, down to your core  
> Yeah, ’till you can’t crawl no more  
> And way down we go-o-o-o-o  

*“Heart-Shaped Box”* by Nirvana (1993)

> Hey  
> Wait  
> I got a new complaint  
> Forever in debt to your priceless advice 

*“Apologize”* by Timbaland, OneRepublic (2007)

> You tell me that you need me  
> Then you go and cut me down, but wait  
> You tell me that you’re sorry  
> Didn’t think I’d turn around and say  
> That it’s too late to apologize  
> It’s too late

#### Cluster 2

Cluster 2 captures songs in which the narrator appears pessimistic and defiant. 

*Mouthful of Diamonds* by Phantogram (2010)
> The world is not round because of you      
> You know I'm not around because of you        
> You've got a mouthful of diamonds     
> And a pocketful of secrets        
> I know you're never telling anyone        
> Because the patterns, they control your mind      
> Those patterns take away my time      
> Hello, goodbye        

*Heavy In Your Arms* by Florence + The Machine (2009)
> My love has concrete feet 
> My love's an iron ball    
> Wrapped around your ankles    
> Over the waterfall    
> I'm so heavy      
> Heavy, heavy in your arms     

*Red* by Catfish and the Bottlemen (2016) 
> How about I change?   
> How about you look at me the same? 
> Hey          
> How about I change?       
> How about you love me again?  


### Case 2: Clusters 3 and 4

Clusters 3 and 4 share medium valence but differ in energy, ranging from medium to high. 
- Cluster 3 (n = 17; valence = 51.3; energy = 49.9) is characterized by medium valence and moderate energy. 
- Cluster 4 (n = 16; valence = 49.3; energy = 84.9) is characterized by medium valence and high energy.

#### Cluster 3

Cluster 3 captures songs in which the narrator appears morally wounded and accusatory.

*labour* by Paris Paloma (2023)
> The capillaries in my eyes are bursting  
> If our love died, would that be the worst thing?  
> For somebody I thought was my saviour  
> You sure make me do a whole lot of labour 

*Cringe* by Matt Maeson (2019)
> She said I'm looking like a bad man, smooth criminal  
> She said my spirit doesn't move like it did before  
> She said that I don't look like me no more, no more  
> I said, "I'm just tired"

*Glue Myself Shut* by Noah Kahan (2020)
> You never asked once   
> No, you never asked why   
> If I was putting things off    
> If I was drinking too much of that red wine  

#### Cluster 4

Cluster 4 captures songs in which the narrator appears wounded and defiant, as acknowledged injury gives way to decisive outward action, such as rejection, blame, or enforced distance.

*Bleed It Out* by Linkin Park (2007)
> This hurts, I won't lie   
> Doesn't matter how hard I try      
> Half the words don't mean a thing      
> And I know that I won't be satisfied        

> I bleed it out, diggin' deeper just to throw it away  

*Black Out Days* by Phantogram (2014)
> Speak in tongues    
> I don't even recognize your face   
> Mirror on the wall        
> Tell me all the ways to stay away     
> Away-ay ya          

*Cute Without The 'E' (Cut From The Team)* by Taking Back Sunday (2002)
> Hoping for the best, just hoping nothing happens  
> A thousand clever lines unread on clever napkins  
> I will never ask if you don't ever tell me    
> I know you well enough to know you'll never love me   

> And all of this was all your fault


### Case 3: Clusters 0 and 5

Cluster 0 (n = 6; valence = 79.5; energy = 72.0) represents the upper extreme and is characterized by high valence and high energy. Cluster 5 (n = 3; valence = 24.3; energy = 28.3) represents the lower extreme and is characterized by low valence and low energy.

#### Cluster 0

Cluster 0 captures songs in which the narrator is morally certain and energized, expressing confrontation without ambivalence.

*Gaslighter* by The Chicks (2020)
> Gaslighter, denier    
> Doin' anything to get your ass farther    
> Gaslighter, big timer     
> Repeating all of the mistakes of your father      
> Gaslighter, you broke me      
> You're sorry, but where's my apology?     
> Gaslighter, you liar      

*Typical Ways* by Culture Wars (2025)
> And I know I adore ya, but I’m no good for ya     
> There’s no way you’re changing my mind               
> And you’re so…        
> Stuck in your typical ways        

#### Cluster 5

Cluster 5 captures songs in which the narrator expresses emotional withdrawal, resignation, or detachment rather than engagement with harm or repair.

*You're So Cold* by Two Feet (2016)
> You are a stranger when I come home       
> You'll never turn your dreams to gold     
> You're so cold        
> You're so cold        

*Leave It* by Teacup Monster (2018)
> You could tell me I’m dumb        
> And I don’t understand        
> But, that’s how I am         
> Just take it      
> Just take it or leave it          

### Cluster Evaluation 

Notably, the clusters organize into two equally sized central groupings. Clusters 1 and 2 together account for 33 songs, as do Clusters 3 and 4, while the remaining clusters occupy the extremes of the valence–energy space (Cluster 0, n = 6; Cluster 5, n = 3).

Taken together, Clusters 1 and 2 reflect low-valence responses that diverge primarily by energy, ranging from defensive frustration to defiant action in response to sustained pressure or perceived inevitability.

Clusters 3 and 4 likewise differ primarily by energy while sharing medium valence. These clusters are organized around moral injury, where harm is recognized and responsibility is assigned, with responses ranging from unresolved accusation to active rejection.

By contrast, Cluster 0, defined by high valence and high energy, reflects affirming or expansive emotional states characterized by moral certainty and activation, while Cluster 5, defined by low valence and low energy, reflects withdrawal, resignation, or emotional collapse.

## Conclusion 

This analysis demonstrates that songs within the moral philosophy playlist cluster not only by affective properties such as valence and energy, but by distinct moral–emotional orientations. By mapping valence to appraisals of harm and energy to response posture, the resulting clusters reveal patterned ways in which distress is processed, expressed, and resolved in popular music.

Across the central clusters, two dominant modes emerge: pessimistic, judgmental responses to sustained pressure (Clusters 1 and 2) and responses organized around moral injury (Clusters 3 and 4). Within each mode, differences in energy distinguish defensive engagement from defiant resolution. These patterns are bounded by two affective extremes: an upper pole characterized by energized moral certainty (Cluster 0) and a lower pole characterized by withdrawal and resignation (Cluster 5).

The initial hypothesis that songs expressing moral judgment would tend toward lower valence was largely supported by the results. Five of the six clusters (Clusters 1–5) exhibited mean valence values ranging from 24.3 to 51.3, indicating that most songs in the playlist occupy pessimistic to moderately neutral emotional orientations. Cluster 0 stood as a notable exception, with a substantially higher mean valence (79.5), despite also exhibiting high energy.

Gaslighter by The Chicks provides a clear illustration of this exception. Although the song centers on a strong moral accusation—explicitly naming deception, denial, and wrongdoing—the narrator expresses that judgment with conviction rather than uncertainty or despair. This stance is reflected in the song’s musical features, which place it in a high-energy, high-valence region of the feature space. Rather than signaling emotional resolution or positivity in a conventional sense, the elevated valence appears to capture moral certainty and decisiveness. This finding highlights that moral judgment in music can be expressed not only through pessimism or distress, but also through energized, affirming confrontation.

Together, these findings suggest that emotional expression in music is structured not only by intensity or positivity, but by how narrators position themselves in relation to harm, responsibility, and agency. Rather than treating valence and energy as purely descriptive features, this framework highlights their role in shaping moral stance, offering a more nuanced account of how distress and resistance are articulated in contemporary song lyrics.