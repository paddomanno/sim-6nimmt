# Simulating a Card Game: 6 nimmt

## Project Overview

This project focuses on simulating and analyzing the performance of different strategies in a game environment. The primary goals are to:

1. Develop various game-playing strategies.
2. Simulate games using these strategies.
3. Analyze the results to determine the effectiveness of each strategy.
4. Visualize the outcomes to gain insights and analyze the performance of each strategy in various playing environments, such as:
   - Determine how the number of players affects strategy effectiveness.
   - Examine how opponents' strategies influence one's own strategy.

## Project Structure

The project is organized as follows:

- **Strategy Functions:** Implementation of different strategies.
- **Simulation Function:** Conducts the simulation of games based on the provided strategies.
- **Analysis Function:** Analyzes the results of the simulations.
- **Visualization:** Generates visual representations of the results to aid in analysis.

## Simulation Framework

### Game Setup

- **Players**: Each game can have between 2 to 10 players.
- **Deck**: Consists of 104 cards numbered 1 to 104. Each card has a number of penalty points associated with it.

### Game Flow

- **Round Setup**: Each player is dealt 10 cards, and four cards are placed face-up to start four rows.
- **Round Steps**: Each round consists of 10 steps, one for each card in the players' hands. At the start of each step, players simultaneously select a card to play.
- **Card Placement**: Cards are placed in rows according to game rules.
- **Penalties**: Players collect cards if they have to place the sixth card in a row.

### Ending a Game

- A game ends after at least one player collects 66 or more penalty points, no matter how many rounds are played. The player with the fewest penalty points wins.

## Strategies Implemented

1. **Random Strategy:** Players make random moves.
2. **Highest First Strategy:** Players prioritize the highest available moves.
3. **Lowest First Strategy:** Players prioritize the lowest available moves.
4. **Midrange Strategy:** Players aim for moves that are neither the highest nor the lowest, but in the middle range.

## Analysis and Metrics

The analysis function examines the results of the simulations to provide insights into the effectiveness of each strategy. Key metrics analyzed include:

- **Win Rate:** The percentage of games won by each strategy.
- **Average Score:** The average score achieved by players using each strategy.

## Insights Gained

The analyses and visualizations provided the following insights:

1. **Success of "Highest First" Strategy:**

   - **Win Rates:** The "Highest First" strategy emerged as the most successful strategy among those tested. In a 3-player scenario, it wins approximately 2 out of 3 games. Even in a 4-player scenario, it maintains a win rate of over 50%.
   - **Effect of More Players:** Increasing the number of players (e.g., to 5 or 6) distributes the win rates more evenly among strategies due to the higher number of participants. However, "Highest First" remains the most successful strategy overall.

2. **Average Penalty Points per Step:**

   - **"Highest First" Performance:** On average, the "Highest First" strategy consistently accrues lower penalty points compared to other strategies throughout the course of a round. Notably, after the first step, it starts off with significantly fewer penalty points. Although it collects penalty points more rapidly up to the fourth step, its penalty accumulation rate slows down thereafter. This trend becomes more pronounced with an increasing number of players.
   - **"Lowest First" Performance:** This strategy begins with the highest penalty points after the first step and in the first half of the round it collects penalty points more slowly than any other strategy. After that though, it accelerates its penalty point accumulation towards the end of the round. Despite occasionally outperforming "Midrange" and "Random" strategies during mid-round, it collects too many penalty points in the last three steps, causing it to consistently lose in this combination of strategies.
   - **"Random" Strategy:** This strategy exhibits a more or less linear penalty point accumulation curve.
   - **"Midrange" Strategy:** While it effectively avoids penalty points at the start of many rounds, after the first three steps, it accumulates penalty points as quickly as the "Random" strategy, resulting in performance that is roughly equivalent to the "Random" strategy.

3. **Performance Against Different Strategy Mixes:**

   - **Focus on "Highest First":** Given its superior performance in previous tests, the analysis focused on how "Highest First" fares against different strategy combinations. In all scenarios, there were four total players, with "Highest First" facing three opponents.
   - **Win Rate Variability:** When competing against three other "Highest First" players, the win rate is predictably 1/4. Against all but one of the other mixes, "Highest First" consistently wins more than 1/4 of the games, with win rates ranging from 0.2 to 0.5. It performs best against the "Random+Lowest+Midrange" combination and 3x Random. The only combination where it performs below the 1/4 threshold is against 3x Lowest, warranting further analysis to understand this anomaly.

4. **Multiple Winners:**
   - **Frequency of Multiple Winners:** When analyzing the count of games with multiple winners, the scenario of playing against 3x "Highest First" results in the highest number of multiple winners. This outcome is expected, as identical strategies tend to perform similarly, increasing the likelihood of matching scores at the end of the game.

## Future Work

Future enhancements could include:

- **Parameter Tuning**: Optimize strategies for better performance.
- **Hybrid Strategies**: Combine different strategies for improved results.
- **Machine Learning**: Explore using machine learning to develop adaptive strategies.
- **Testing more environments**: Create heatmaps or other visual aids to show strategy effectiveness in different environments.
