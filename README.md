# langchain-use

Decorators to make some limited langchain functionality more functional.

## Usage

```python
from main import use_prompt, use_llm
from langchain import OpenAI

@use_llm(OpenAI())
@use_prompt
def assign_to(task):
    return f'''
        Determine whether the listed task should be assigned to Human Secretary or Computer Algorithm.

        Task: Summarize this report.
        Assign to: Human Secretary

        Task: Compute total profit and loss.
        Assign to: Computer Algorithm

        Task: {task}
        Assign to:
    '''.strip()

print(assign_to.predict(task='Write a poem'))
```