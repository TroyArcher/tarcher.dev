---
title: "Hackathon 2025"
date: 2026-01-18T12:30:00-05:00
draft: false
tags: ["backend", "ai", "hackathon"]
categories: ["Software Engineering"]
author: "Troy Archer"
showToc: true
TocOpen: false
hidemeta: false
comments: false
description: "Welcome to my Hackathon 2025 project! This project is designed to revolutionize the way we handle message validation in the telecommunications industry."
canonicalURL: "https://tarcher.dev/posts/hackathon-2025/"
disableHLJS: false
disableShare: false
hideSummary: false
searchHidden: false
ShowReadingTime: true
ShowBreadCrumbs: true
ShowPostNavLinks: true
ShowWordCount: true
ShowRssButtonInSectionTermList: true
UseHugoToc: true
cover:
    image: "<image path/url>"
    alt: "Scalable web architecture diagram"
    caption: "<text>"
    relative: false
    hidden: true
editPost:
    URL: "https://github.com/TroyArcher/tarcher.dev/blob/main/content"
    Text: "Suggest Changes"
    appendFilePath: true
---

# Hackathon 2025 - Handbrake
Welcome to my Hackathon 2025 Handbrake project! This project was developed as part of a challenging 48-hour hackathon, designed to push the boundaries of rapid innovation. It aims to revolutionize the way we handle message validation in the telecommunications industry. By leveraging advanced AI and machine learning techniques, we provide a robust solution for ensuring message content aligns with predefined use cases and summaries.

We had a team of 5 engineers who worked long hours to bring this project to life and we succeeded far beyond what we had expected going into the hackathon!

## Why We Built It
In the vast sea of options for reaching customers, SMS Marketing is like a cruise ship. With over 6 billion SMS users globally and open rates of up to 98%, SMS Marketing has broad reach and wide consumer appeal. Even better, SMS Marketing offers an array of options for campaigns, from short codes to 10DLC to toll-free and alphanumeric.

When your text messaging diverges from your registered use case, it’s called “campaign drift.”

Campaign drift is more than just an annoyance for customers. For companies, carriers, and aggregators, campaign drift can cause brand damage, additional expenses, and even business texting compliance issues.

## What is Campaign Drift?
Campaign drift happens when a number previously registered for one use case is used for content unrelated to that original use case. For example, a medical office that registers a number for appointment notices cannot use that same number for educational content or promotional offers.

## Why Does Campaign Drift Matter?
Consumers, carriers, and aggregators are increasingly diligent about stopping spam texts and robotexts. According to the FCC, text scams and complaints have risen dramatically in recent years. In 2022, the agency reported almost 19,000 robotext complaints—a 500% increase from 2015.

When campaigns drift from registered use cases, carriers, aggregators, and providers may suspend the campaign. Suspended campaigns can result in lost sales, disgruntled customers, and fees and penalties for non-compliance with business texting regulations. Companies then incur new costs to register a new campaign.

## How to Avoid Campaign Drift
Avoiding campaign drift isn’t impossible. Here are a few tips to help brands maintain business texting compliance:

*   Be clear about the original campaign purpose, and choose the correct use case when registering.
*   Text platforms should practice Know Your Customer (KYC) protocols, and brands need to be prepared to provide appropriate proofs for compliance.
*   Consider mixed use campaigns or special use campaigns for campaigns that may have multiple uses.
*   For separate use cases, create a brand new campaign or toll-free verification to ensure texts are legitimate and compliant with business texting regulations.
*   Familiarize yourself with business texting compliance rules from the Cellular Telecommunications Industry Association (CTIA) and relevant government agencies, such as the FCC.

## How It Works
Our project utilizes a sophisticated architecture combining Flask for the web framework, OpenAI's powerful language models for natural language processing, and LangChain for efficient management and retrieval of relevant examples from a vector store. The system operates through the following technical flow:

*   Receiving a message and its associated use case and summary.
*   Validating the presence of required fields.
*   Checking the validity of the use case.
*   Retrieving relevant examples for that use case from a pre-built data store.
*   Using OpenAI to analyze the message content and provide a confidence score on its alignment with the use case and summary.

## What is RAG?
RAG (Retrieval-Augmented Generation) is a technique that combines the power of retrieval-based methods with generative models to provide deeper context and more accurate responses. In our project, we use RAG to enhance the capabilities of our language model by retrieving relevant examples from a vector store. This allows the model to generate more contextually accurate and reliable validation results.

## How We Use RAG
In our project, RAG is used to augment the language model's understanding by providing it with similar examples from our database. This helps the model to better understand the context and nuances of the message content, leading to more accurate validation and detection of campaign drift.

## RAG and Vectorized Databases for Enhanced Accuracy

To significantly improve the accuracy and contextual understanding of our message validation, we implemented RAG in conjunction with a vectorized database. This approach allows our language model to go beyond its pre-trained knowledge by dynamically retrieving highly relevant examples from a specialized data store. We pass these vectorized examples into the prompt as embeddings, which provides the model with concrete, real-world context to inform its analysis and confidence scoring efficiently.

Here's how it enhances accuracy:

1.  **Contextual Relevance**: When a message is submitted for validation, instead of relying solely on the LLM's general understanding, we first query a vectorized database. This database stores embeddings of various use cases and message examples. By performing a similarity search, we retrieve the most contextually relevant examples.

    ```python
    # app.py
    # Get relevant examples using RAG
    relevant_examples = message_validator.get_relevant_examples(
        data['message_content'],
        data['use_case']
    )
    ```

2.  **Augmented Prompting**: The retrieved examples are then seamlessly integrated into the prompt provided to the OpenAI language model. This enriched prompt gives the LLM specific, real-world context pertinent to the current validation task, enabling it to make more informed and accurate judgments.

    ```python
    # app.py
    # Prepare context for the LLM
    context = "\n".join([
        f"Similar example {{i+1}}: {{example[0].page_content}} (similarity: {{example[1]:.2f}})"
        for i, example in enumerate(relevant_examples)
    ])

    # Enhanced prompt with RAG context
    developer_prompt = f"""You are a discriminator application. You work in the telecommunications industry validating whether a message_content that is sent corresponds to the preset use_case and use_case_summary.
    Your goal is to identify when messages drift from this use_case and use_case_summary. Give a confidence score from 0 to 100 on how well the message_content fits the use_case and use_case_summary.

    Use case: {data['use_case']}
    Use case summary: {data['use_case_summary']}

    Here are similar examples from our database:
    {context}

    OUTPUT MUST HAVE TO ONLY RETURN UNFORMATED JSON. Respond with "confidence_score" (int), "score_positive_reasons" (array), "score_deduction_reasons" (array).
    """
    ```

3.  **Reduced Hallucinations and Improved Reliability**: By grounding the LLM's responses in specific, retrieved data, RAG significantly reduces the likelihood of "hallucinations" or inaccurate inferences. The model's confidence scores and reasoning are thus more reliable and directly attributable to established examples, leading to a more robust validation system.

Our synthetic data generators, mentioned previously, were crucial in populating this vectorized database with a diverse and representative set of use case examples, further bolstering the system's accuracy.

## Model Used
We used OpenAI's gpt-4o-mini model for this project. We chose it because it was small, fast, and cost effective, which was important given the time constraints of the hackathon. It provided us with an effective solution for our message validation and synthetic data generation needs without the overhead or price of larger models.

## Flask App & API
Our Flask application serves as the robust backbone of our message validation system, exposing a RESTful API endpoint for real-time message validation against predefined use cases and summaries. The API operates as follows:

*   Base URL: http://localhost:4040
*   Endpoint: /validateMessage
*   Method: POST
*   Input: JSON payload containing use_case, use_case_summary, and message_content.
*   Process:
    *   Validates the presence of required fields.
    *   Checks the validity of the use case.
    *   Retrieves relevant examples using RAG.
    *   Uses OpenAI to analyze the message content and provide a confidence score.
*   Output: JSON response with a confidence score and reasons for score deductions if the message does not fit the use case.

This API helps solve the problem of campaign drift by providing a robust mechanism for validating message content, ensuring compliance with business texting regulations, and preventing brand damage and additional expenses.

## Why is it called Handbrake?
When driving in hazardous conditions, a handbrake can be used to quickly and effectively steer your car if it begins drifting off the road. Likewise, this tool can be used to help course correct sending campaigns that are drifting from their original stated criteria.

# Conclusion
The Handbrake project is a powerful tool for combating campaign drift in the telecommunications industry. A team of five engineers built this project in just 48 hours for our Hackathon 2025, and it has the potential to make a significant impact on how businesses ensure compliance with business texting regulations and maintain brand integrity. By leveraging AI, RAG, and a robust Flask API, Handbrake provides a comprehensive solution for validating message content and preventing campaign drift.

We ended up placing 2nd in the Hackathon out of 29 submitted projects. It's incredibly rewarding to see the hard work and innovation of our team recognized, and we're excited about the potential impact of Handbrake in the industry. We look forward to further developing this project and exploring new ways to enhance its capabilities in the future. Shoutout to my team =)