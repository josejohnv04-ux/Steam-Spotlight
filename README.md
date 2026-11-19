# Steam Spotlight

My app helps Steam’s store team decide what games should be on the front page by highlighting games with exceptionally high positive review percentages (above 85%) that offer deep promotional discounts.

> A course project for **MIST 4600: Computer Programming in Business** at the University of Georgia's Terry College of Business (Fall 2026).

## Problem
Steam’s storefront merchandising team must decide which games to feature on the front page to maximize player engagement and store revenue. With thousands of titles on the platform, manually cross-referencing player ratings, active player volume, and live deal or critic data across separate sources is slow and inconsistent. Without an automated ranking tool, high-converting games with strong community momentum or rare price drops can easily be overlooked.

## What it does
My app answers three questions:
1. **Sub-question 1:** Recency: Which recent releases maintains   active momentum?
2. **Sub-question 2:** Critics: What do critics say about them?
3. **Sub-question 3:** Players: Which of them have the most players?

## Data
The [Steam Games Dataset](https://www.kaggle.com/datasets/artermiloff/steam-games-dataset) on Kaggle, collected in March 2025. The dataset is shared under the MIT License by its creator, artermiloff. This repo uses `steam_games.csv`, a smaller file made for the course: the 1,000 games with the most reviews.

## Built with
- Python and pandas, in Google Colab
- My outside tool:Google Gemini API

## How to run it
Click Open in Colab above, or open family_game_night_picker.ipynb from this repository in Google Colab.
Put steam_games.csv (in this repository) in your Google Drive, in the same folder as the notebook.
Get a free Gemini API key at aistudio.google.com (use a personal Gmail account). In Colab, click the key icon on the left (Secrets), add a secret named GOOGLE_API_KEY with your key as its value, and turn on Notebook access.
Choose Runtime → Run all. Allow access to Google Drive when Colab asks. The last cell takes about 30 seconds.

## Example output
                  name  release_year  num_reviews_total  pct_pos_total
9        Apex Legends™          2020             983230             67
10  Black Myth: Wukong          2024             825621             96
12          ELDEN RING          2022             749606             92
14      Cyberpunk 2077          2020             729016             85
15       HELLDIVERS™ 2          2024             716489             76

## AI Use Disclosure

* **I used AI tools:** Yes
* **Tools:** Gemini
* **What I asked:** to help structure the notebook's code and markdown cells around my proposal, write helper functions for my sub-questions and Gemini API calls, build the `FrontPagePick` class, and troubleshoot Colab setup and Secret errors.
* **What I added, changed, or fixed in the AI's output:** chose the target user, business decision, and custom recency sub-question; defined the filtering cutoffs (2020–2024 release years, 80%+ positive reviews, and 2,000,000+ estimated owners); customized the `recent_momentum` and `filter_high_players` functions; configured the `GOOGLE_API_KEY` secret and Drive/GitHub data loading; and verified all outputs against `steam_games.csv`.
* **What I designed and wrote entirely myself:** the project concept (*Steam Spotlight*), the three sub-questions, the filtering thresholds, and the final front-page recommendation based on the live results.
* **I understand every line of code I am submitting:** Yes

## Author
John Jose
