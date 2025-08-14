# EmpatheticCodeReviewer

Follow the steps in the EmpatheticCodeReviewer.ipynb notebook

Brief on how to run the Reviewer:
1. Set up the notebook in your Jupyter environment
2. Change the GROQ API Key or change the LLM
3. Run all cells from start to end to get the markdown response
4. You can change the example_input in the last cell to test the performance of the Reviewer

Explanation of Working:
1. Prompt Engineering: Few shot examples, Instructions as per requirements, Enforcing Format, Suggesting Tool usage to search for documentation links.
2. ReAct Langchain agent that takes the input the severity analysis through the same llm done in previosly, the above engineered prompt, code snippet and review comments
3. It gnerates the Reviwed and modified output as per the requirement of the problem statemnet
