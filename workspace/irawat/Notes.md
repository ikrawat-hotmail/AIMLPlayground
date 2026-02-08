Run ollama locally on windows
1. download ollam
2. Run a very small slm model on a local PC:
  ollama.exe run gemma:2b
4. Use python to connect with gemma:2b
5.
```markdown
```python
import requests

def chat_with_ollama(prompt):
    response = requests.post(
        "http://localhost:11434/api/generate",
        json={"model": "gemma:2b", "prompt": prompt}
    )
    for line in response.iter_lines():
        if line:
            data = line.decode("utf-8")
            print(data)

chat_with_ollama("Hello, how are you?")
