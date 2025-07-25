Will Your Next Medical Supplier Accept Your Insurance? The Data Might Have the Answer
Gcapanna
Gcapanna
3 min read
·
6 days ago





Zoom image will be displayed

Navigating healthcare can feel like a maze. One of the most common frustrations is finding a pharmacy or medical supplier, only to discover they don’t accept your insurance plan. This isn’t just an inconvenience; it’s a real barrier to accessible care.

This frustration sparked a question: can we use data to bring some clarity to this problem? I decided to find out by analyzing a public dataset from the Centers for Medicare & Medicaid Services (CMS) and following a structured data science process to see what insights we could uncover.

The Approach: From Raw Data to Real Answers
Instead of just looking at the data, I followed the CRISP-DM framework, a roadmap that guides an analysis from a business question to a final, evaluated result. My investigation was driven by three key questions:

Geography: Where are most suppliers located?
Accessibility: What percentage of them actually accept assignment?
Prediction: Can we build a model to predict this behavior?
The Challenge: Cleaning Messy, Real-World Data
Before any analysis, the data needed significant preparation. It was messy, with many columns having over 80% of their values missing.

A crucial decision had to be made: should I try to “fill in” the blanks (a process called imputation) or remove them? With so much data missing, filling it in would have meant inventing information, leading to a biased and unreliable model. The most honest approach was to remove these incomplete columns, ensuring our analysis was built on a foundation of real, trustworthy data. This preparation step was vital for the integrity of the results.

The Discoveries: Answering Our Key Questions
After cleaning the data, clear answers to our initial questions began to emerge.

1. Geographic Hubs Are Real

Unsurprisingly, suppliers are not evenly distributed. There’s a heavy concentration in California, Texas, and Florida. This confirms that access to healthcare suppliers is densest in highly populated states, a critical factor for both patients and policymakers.

Zoom image will be displayed

2. Accessibility Is a 50/50 Gamble

This was the most striking finding. The data shows an almost even split: 51.6% of suppliers do NOT accept assignment, while only 48.4% do. This single statistic paints a stark picture of the healthcare landscape. For patients, it means their choices are effectively cut in half from the outset, purely based on this acceptance policy.


3. Yes, We Can Predict the Future (with 74% Accuracy)

The most exciting part was building a machine learning model (a RandomForestClassifier) to see if we could predict a supplier's choice. After training it on thousands of examples, the model was able to predict whether a supplier would accept assignment with 74% accuracy.

To bring this to life, I posed a hypothetical scenario: a new pharmacy, “PharmaHealth,” opens in Pharr, Texas. What would it likely do? The model’s prediction was clear: it would most likely not accept assignment.

Conclusion: From Data to Decision-Making
This project proves that data science is more than just code and algorithms; it’s a process for turning complex questions into clear, actionable insights. While a 74% accuracy model is just a starting point, it demonstrates that we can use publicly available data to make the often-opaque world of healthcare a little more transparent.

For those interested in the technical details, the full analysis is available in my GitHub repository.