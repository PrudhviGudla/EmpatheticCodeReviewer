# EmpatheticCodeReviewer

## Overview
EmpathicCodeReviewer is a LangChain-based agent that transforms harsh code review comments into empathetic, constructive feedback. It utilizes AI to reframe criticism in a positive light while maintaining technical accuracy and providing educational explanations, accompanied by relevant documentation.

## Features
Core Functionality
Empathetic Transformation: Converts harsh review comments into supportive, encouraging feedback

Severity Classification: Automatically categorizes comments as CRITICAL, MODERATE, or MINOR

Technical Documentation: Uses web search to find relevant programming resources and best practices

Tone Adaptation: Adjusts response tone based on comment severity

Code Examples: Provides concrete code improvements with inline explanations

## Technical Features
ReAct Agent Architecture: Uses reasoning and acting cycles for systematic processing

Tool Integration: Incorporates DuckDuckGo search for documentation lookup

Custom Agent Executor: Implements stopping conditions to prevent infinite loops

Error Handling: Graceful fallback when search tools fail

Token Management: Optimized search results to prevent token overflow

## Installation and Usage
```
pip install langchain-groq langchain-community duckduckgo-search
```
```
from empathic_code_reviewer import EmpathicCodeReviewer

# Initialize the reviewer
reviewer = EmpathicCodeReviewer()

# Prepare input data
example_input = {
    "code_snippet": "function calculateTotal(items) {\n var sum = 0;\n for (var i = 0; i < items.length; i++) {\n sum += items[i].price * items[i].qty;\n }\n return sum;\n}",
    "review_comments": [
        "Use const/let instead of var. This is terrible practice.",
        "Function name is too generic.",
        "No input validation - this will crash with null items.",
        "Consider using reduce() for functional programming style."
    ]
}

# Generate empathetic review
result = reviewer.generate_empathetic_review(example_input)
print(result)
```

Input Format
json
{
    "code_snippet": "string - The code to be reviewed (use \\n for line breaks)",
    "review_comments": [
        "string - First review comment",
        "string - Second review comment",
        ...
    ]
}
Output Format
The tool generates structured feedback with:
Positive Rephrasing: Encouraging version of the original comment
The 'Why': Technical explanation with analogies
Suggested Improvement: Concrete code examples with comments
Additional Resources: Relevant documentation links
Overall Feedback Summary: Motivational conclusion

## API Key Setup
Replace the API key in the code cell:

```
llm = ChatGroq(
    model="llama3-8b-8192",
    temperature=0.7,
    max_tokens=3000,
    api_key="your_groq_api_key_here"  # Replace with your key
)
```
