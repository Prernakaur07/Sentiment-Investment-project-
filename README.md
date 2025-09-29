Project Report: Sentiment Investment Project
1. Introduction

The Sentiment Investment Project is a financial news analysis system designed to help investors gain insights into market trends, stock behavior, and cryptocurrency movements. By leveraging data from Reddit, financial news websites, and NewsAPI, the system aggregates real-time headlines, filters them for relevance, and performs sentiment analysis with investment recommendations using Groq LLM models.

This ensures investors receive concise, actionable insights regarding whether to Buy, Sell, or Hold assets based on current news sentiment.

2. Objectives

Automate the process of collecting finance-related headlines from multiple sources.

Filter quality headlines by focusing only on investment, trading, and financial topics.

Perform sentiment analysis (Positive, Negative, Neutral) with a recommendation system (Buy/Sell/Hold).

Provide clear explanations to support investor decisions.

Develop an API system that can be integrated with dashboards, bots, or financial applications.

3. Technical Stack & Skills Used
Languages & Frameworks

Python (core programming language)

FastAPI (for building REST APIs and endpoints)

Uvicorn (ASGI server for running FastAPI apps)

Libraries & Tools

Pydantic → Data validation for API inputs/outputs.

Requests & httpx → Fetching data from external APIs.

BeautifulSoup (bs4) → Web scraping financial headlines from websites.

Selenium + WebDriver Manager → Advanced scraping for dynamic pages.

Pandas → Data handling and debugging.

Regex (re) → Filtering low-quality or irrelevant headlines.

Groq LLM (Llama 3.3-70B) → Sentiment and recommendation generation.

PRAW (Python Reddit API Wrapper) → Fetching Reddit finance-related posts.

Middleware & Config

CORS Middleware → Allow cross-origin requests for frontend integration.

4. Project Workflow
Step 1: Data Collection

Reddit API (PRAW)
Fetches posts from finance-related subreddits. Only headlines with minimum upvotes and financial keywords are considered.

Web Scraping (BeautifulSoup, Selenium)
Extracts headlines from Yahoo Finance, MarketWatch, Google Finance, Investing.com, and other financial portals using CSS selectors.

NewsAPI Integration
Pulls top business/financial headlines filtered by keywords like stocks, investment, bitcoin, economy.

Step 2: Quality Filtering

Headlines are validated using regex rules to remove irrelevant posts (e.g., memes, general discussions, non-financial threads).

Headlines must meet length criteria (8–50 words).

Only finance-related keywords (e.g., stock, trading, earnings, profit, market) are accepted.

Step 3: Sentiment & Recommendation Analysis

Headlines are sent to the Groq LLM with strict instructions:

Classify Sentiment → Positive / Negative / Neutral.

Give Recommendation → Buy / Sell / Hold.

Provide short 2–3 sentence explanation with market context.

Discard irrelevant news by labeling them NOT_QUALITY.

Step 4: Output & API Integration

Final structured response is returned as a JSON object:

{
  "headline": "Tesla stock surges after strong Q3 earnings",
  "sentiment": "Positive",
  "recommendation": "Buy",
  "explanation": "Strong earnings boosted investor confidence, indicating growth potential. Uptrend likely to continue."
}


API endpoints:

/reddit-headlines/ → Analyze Reddit finance headlines.

/web-headlines/ → Scrape & analyze financial websites.

/news-headlines/ → Analyze financial news via NewsAPI.

5. Results & Outcomes

The system can extract up to 40 Reddit headlines and 15–20 news/web headlines in a single run.

Headlines are analyzed and returned with sentiment, recommendation, and reasoning.

Eliminates noise from irrelevant posts and ensures only investor-focused news is displayed.

Can be integrated with:

Investor dashboards (real-time sentiment tracking).

Trading bots (for decision-making).

Market research tools.

6. Use Cases

Investors & Traders → Quick insights into market sentiment before making trades.

Financial Analysts → Summarized news with structured investment recommendations.

News Aggregators → Provides AI-driven sentiment tagging for financial headlines.

Portfolio Managers → Helps in decision-making by tracking news impacts on specific assets.

7. Key Learnings & Technical Skills Gained

Built end-to-end API system with FastAPI.

Hands-on with Reddit API (PRAW) and NewsAPI integration.

Practical web scraping using BeautifulSoup & Selenium.

Applied prompt engineering for financial sentiment analysis with Groq LLM.

Strengthened data filtering, text processing, and regex handling.

Learned CORS, async requests, and API deployment with Uvicorn.

8. Conclusion

The Sentiment Investment Project successfully integrates APIs, web scraping, and AI-driven sentiment analysis to deliver investor-focused financial insights. It automates the collection, filtering, and evaluation of finance headlines into actionable insights. This system is a powerful foundation for AI-powered financial analytics platforms, providing investors with a competitive advantage in decision-making.
