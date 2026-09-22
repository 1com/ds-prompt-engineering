# Prompt Engineering with LangChain

A hands-on workshop on prompt engineering, the practice of designing inputs that guide Large Language Models toward the outputs you want. You will work through three notebooks using the LangChain framework with Groq's API and OpenAI's open-weight gpt-oss models, building from your first prompt template up to few-shot prompting and prompt testing.

## Learning Objectives

By the end of this repository, you should be able to:

- Integrate a Groq-hosted gpt-oss model with LangChain and create prompt templates with dynamic input variables.
- Build chains by piping components together (`prompt | llm | output_parser`) and invoke them for single and batch queries.
- Apply the four-part prompt structure (instruction, context, input, output indicator) to real tasks.
- Use few-shot prompting and `FewShotPromptTemplate` to teach the model a desired output format.
- Test and iterate on prompts, comparing a baseline against stricter instructions on a small evaluation set.

## Learning Path

Start with the prompt engineering workflow, work through the three notebooks in order, then read the applications and project ideas:

| File / Folder | Description |
|---|---|
| [**1 - Prompt Engineering Workflow**](1_prompt_engineering_workflow.md) | Primer on the pipeline and the four-part prompt structure. |
| [**2 - Intro to LangChain**](2_intro_langchain.ipynb) | LangChain core components, connecting a Groq model, prompt templates, and chains. |
| [**3 - Prompt Engineering with LangChain**](3_langchain_prompt_engineering.ipynb) | The four-part prompt structure in practice, context-based answering, and few-shot prompting. |
| [**4 - Prompt Testing and Iteration**](4_prompt_testing_and_iteration.ipynb) | Building an evaluation set and comparing a baseline prompt against stricter instructions. |
| [**5 - Real-World Applications and Project Ideas**](5_real_world_and_project_ideas.md) | How prompt engineering is used in production, plus projects to practise. Read this last. |

### Additional Folders and Files

| File / Folder | Description |
|---|---|
| [**Assets**](assets/) | Images used in the documentation. |
| [**Solutions**](solutions/) | Reference solutions. |
| [**.env.example**](.env.example) | Template for the environment variables you need to provide. |
| [**pyproject.toml**](pyproject.toml) | Project configuration and dependencies. |
| [**uv.lock**](uv.lock) | Dependency lock file. |

## Setup

> [!NOTE]
> Throughout these steps, text in angle brackets like `<repo-name>` is a **placeholder**. Replace it, including the `< >` brackets, with your own value. For example, `cd <repo-name>` becomes `cd ds-prompt-engineering`.

### 1. Create the Repository from the Template

Click **Use this template** on GitHub.

When creating the repository:

- Set yourself as the **Owner**
- Choose a repository name
- Disable **Include all branches**
- Click **Create repository**

> [!IMPORTANT]
> If you are working in pairs or groups, only **one person** should complete this step.

---

### 2. Add Collaborators (Pairs/Groups Only)

If working with teammates:

1. Open the repository on GitHub
2. Go to **Settings → Collaborators**
3. Add your teammates as collaborators
4. Share the repository link with your team

Teammates should accept the invitation before continuing.

---

### 3. Clone the Repository

Copy the SSH URL from the **Code** button on GitHub, then run:

```bash
git clone <copied-ssh-url>
```

The copied SSH URL will look like `git@github.com:<your-username>/<repo-name>.git`.

---

### 4. Move into the Project Folder and Install Dependencies

This installs all dependencies and creates a virtual environment in (`.venv/`).

```bash
cd <repo-name>
uv sync
```

---

### 5. Add Your Groq API Key

The notebooks call the Groq API, so you need a free API key.

1. Create a free account at the [Groq Console](https://console.groq.com/playground) and generate an API key (no credit card required).
2. Confirm that the `openai/gpt-oss-20b` model is enabled for your Groq project.
3. Copy the example file and fill in your key:

```bash
cp .env.example .env
```

Then edit `.env` and set your key:

```text
GROQ_API_KEY=<your-groq-api-key>
```

> [!CAUTION]
> Your `.env` file holds a secret and must never be committed. Only `.env.example`, with placeholder values, belongs in the repository.

---

### 6. Open the Notebooks

> [!NOTE]
> Make sure you open VS Code from the project root so it automatically detects the environment created by `uv sync`.

Launch VS Code in the project root folder:

```bash
code .
```

Then open a notebook and select the Python environment created by `uv sync` as the kernel.


## References & Further Reading

- [**LangChain Documentation**](https://docs.langchain.com/oss/python/langchain/overview): The official LangChain guide for building LLM applications.
- [**Prompt Engineering Guide**](https://www.promptingguide.ai/): A thorough, vendor-neutral reference for prompting techniques.
- [**LangChain GitHub Repository**](https://github.com/langchain-ai/langchain): The framework's source, examples, and issues.
- [**Groq Console**](https://console.groq.com/playground): Where you create your API key and test models in the playground.