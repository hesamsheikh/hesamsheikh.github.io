---
layout: page
title: Collaborative AI Agents for Job Applications
description: Implementing AI Agents to Enhance Your CV and Cover Letter
img: assets/img/ai_agents.jpg
importance: 1
category: LLM
---
### Enhancing Your Job Application Process

AI agents are powerful tools designed to automate complex tasks, and in this project, I implemented a team of AI agents to assist with the job application process by refining CVs and cover letters. Here’s how it works:

Implementation Overview
Using CrewAI, I created four AI agents, each with a specific role:

Job Crawler: Extracts key information from a job posting URL, focusing on job requirements and qualifications.
CV Modifier: Enhances the CV by tailoring it to the job description provided by the Job Crawler.
Cover Letter Modifier: Modifies the cover letter in a similar way, aligning it with the job description.
Recruiter: Evaluates the modified CV and cover letter, providing feedback and a suitability score out of 100.
Setting Up the Agents
To start, I initialized the model using GPT-4-turbo and defined custom tools for reading PDFs and web pages. Each agent was assigned a specific role, goal, and backstory, with tools tailored to their tasks.

{% raw %}
```python
# Example code to define an agent
job_crawler = Agent(
    role='Job Description Crawler',
    goal='Extract the relevant job description, requirements and qualifications',
    backstory='Specialized in parsing HTML and retrieving important information from it',
    tools=[get_webpage_contents],
    llm=model
)
```
{% endraw %}

Task Assignment
Each agent was given a specific task, such as extracting job information or modifying the CV. These tasks were interconnected; for instance, the CV and cover letter modifications depended on the job details extracted by the Job Crawler.

{% raw %}
```python
def cv_modifying(cv_path):
    return Task(
        description=f"Modify the CV at {cv_path} to emphasize key skills required by the job.",
        agent=cv_modifier,
        expected_output="A CV tailored for the job description",
    )
```
{% endraw %}

Running the Agents
After setting up the agents and tasks, I created a crew and initiated the process. The agents collaborated to modify the CV and cover letter, with the Recruiter agent evaluating the final output.

{% raw %}
```python
# Start the agent process
crew = Crew(
    agents=[job_crawler, cv_modifier, cover_letter_modifier, recruiter],
    tasks=[extract_job_information_task, cv_modifying_task, cover_letter_modifying_task, evaluate],
)

result = crew.kickoff()
```
{% endraw %}

Results
The agents successfully refined the CV and cover letter to better fit the job description. The Recruiter agent provided a final score, indicating how well-suited the application was for the job. Here’s a sample output from the Cover Letter Modifier agent:

"Now I have the content of the original cover letter. I need to tailor this cover letter to specifically address the job opening at..."

The recruiter agent gave a score of 92 out of 100, reflecting a strong match between the candidate's credentials and the job requirements.

Conclusion
This project demonstrates how AI agents can automate the tedious process of tailoring job applications, offering a practical example of collaborative AI in action.

<div class="row justify-content-sm-center">
  <div class="col-sm-8 mt-3 mt-md-0">
    {% include figure.liquid path="assets/img/ai_agent2.jpg" title="AI Agent Workflow" class="img-fluid rounded z-depth-1" %}
  </div>
</div>
<div class="caption">
    The AI agents collaborated to modify the CV and cover letter, with each agent performing a specific task.
</div>


[Read the Full Article in Detail](https://towardsdatascience.com/a-comprehensive-guide-to-collaborative-ai-agents-in-practice-1f4048947d9c)