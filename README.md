# Inference-Providers-for-google-t5-t5-base
Inference Providers for google-t5/t5-base

# 🌍 Hugging Face Translation Example

This project demonstrates how to use the Hugging Face `InferenceClient` to translate text using a Hugging Face model.

## 📋 Requirements

Before running the code, make sure you have:

- Python 3.8 or newer
- A Hugging Face account
- A Hugging Face API token

## 📦 Installation

Install the Hugging Face Hub library:

```bash
pip install -U huggingface_hub
```

## 🔑 Set Your Hugging Face Token

You need to create a Hugging Face access token and store it as an environment variable named `HF_TOKEN`.

### Windows PowerShell

```powershell
$env:HF_TOKEN="your_huggingface_token"
```

### macOS / Linux

```bash
export HF_TOKEN="your_huggingface_token"
```

> ⚠️ Never share your API token or upload it directly to GitHub.

## 💻 Code

```python
import os
from huggingface_hub import InferenceClient

client = InferenceClient(
    provider="hf-inference",
    api_key=os.environ["HF_TOKEN"],
)

result = client.translation(
    "Меня зовут Вольфганг и я живу в Берлине",
    model="google-t5/t5-base",
)

print(result)
```

## ▶️ Run the Program

Save your Python code in a file, for example:

```text
translation.py
```

Then run:

```bash
python translation.py
```

## 📝 Example Input

The example sends this Russian text:

```text
Меня зовут Вольфганг и я живу в Берлине
```

Which means approximately:

```text
My name is Wolfgang and I live in Berlin.
```

## ⚙️ How It Works

1. The program imports `InferenceClient` from `huggingface_hub`.
2. Your Hugging Face API token is loaded from the `HF_TOKEN` environment variable.
3. An `InferenceClient` is created using the `hf-inference` provider.
4. The `translation()` method sends the text to the specified model.
5. The translated result is returned and printed.

## 🔐 Environment Variables

This project uses:

```text
HF_TOKEN
```

Make sure this environment variable is set before running the script.

## 📚 Technologies Used

- Python
- Hugging Face Hub
- Hugging Face Inference API

## 📄 License

This project is provided for educational purposes.
