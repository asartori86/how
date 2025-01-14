# **How-to Command-Line Assistant**

This project provides a command-line tool to answer Linux command-line and scripting-related queries. Bash is the default language if not requested otherwise. It uses OpenAI's GPT model to generate concise, code-focused responses.

---

## **Features**
- **Natural Usage**: Invoke the tool as if starting a sentence with "how to...".
- **OpenAI API Integration**: Leverages GPT for intelligent responses.
- **Simulated Typing**: Outputs results character by character for an engaging experience.
- **JSON Parsing**: Extracts and formats relevant code or answers.

---

## **Requirements**
- Python 3.6 or later
- An OpenAI API key

---

## **Dependencies**
 - Python sdk package `openapi`
---

## **Setup**

### **1. Set the OpenAI API Key**
Export your OpenAI API key as an environment variable:

```bash
export OPENAI_API_KEY="your_openai_api_key"
```

### **2. Add to PATH**
Move the `how` script to a directory in your `PATH`, such as `~/.local/bin`, for easy access:

```bash
mv how ~/.local/bin/
```

Alternatively, you can add the directory containing `how` to your `PATH` environment variable. For example, if the script is in `~/scripts`, add the following line to your `~/.bashrc` or `~/.zshrc`:

```bash
export PATH="$PATH:~/scripts"
```

Then reload your shell configuration:
```bash
source ~/.bashrc
```

---

## **Usage**

Invoke the tool directly writing the query:

```bash
how <your-query>
```

### **Examples**
#### List All Running Processes
```bash
$ how to list all running processes

ps aux

```

#### Find the biggest directories
```bash

$ how to find the 5 biggest directories in my home

du -ah ~ | sort -rh | head -n 5
```

---

## **Customization**
- **Typing Speed**: Adjust the `simulated_typing` function in `how_to.py` to change the typing effect speed.
- **API Response Creativity**: Modify the `temperature` parameter in the Python script for more deterministic or creative responses.

---

## **License**
This project is licensed under the MIT License. Feel free to use, modify, and distribute it.
