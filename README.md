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
#### Example 1: Create a New Directory
```bash
./how to create a new directory
```

**Output** (simulated typing):
```bash
mkdir <directory-name>
```

#### Example 2: List All Running Processes
```bash
./how to list all running processes
```

**Output** (simulated typing):
```bash
ps aux
```

---

## **File Structure**
- `how`: Bash wrapper script for easy usage.
- `how_to.py`: Python script that interacts with the OpenAI API.

---

## **How It Works**

1. **Input**: The Bash script forwards user queries to the Python script.
2. **Query Formation**: The Python script formats the query as a question.
3. **OpenAI API Interaction**: Sends the query to the GPT model with specific instructions for concise, JSON-formatted responses.
4. **Response Handling**: Extracts the code snippet from the response and displays it via simulated typing.

---

## **Customization**
- **Typing Speed**: Adjust the `simulated_typing` function in `how_to.py` to change the typing effect speed.
- **API Response Creativity**: Modify the `temperature` parameter in the Python script for more deterministic or creative responses.

---

## **License**
This project is licensed under the MIT License. Feel free to use, modify, and distribute it.
