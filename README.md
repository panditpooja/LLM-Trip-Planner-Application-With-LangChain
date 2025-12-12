# Trip Planner Application with LangChain

A simple trip planner application built with LangChain that generates personalized trip plans based on destination and user preferences. The application uses OpenRouter API to access various LLM models.

## Features

- 🗺️ Generate personalized trip plans for any destination
- 🎯 Customize plans based on user preferences (museums, cafes, nightlife, etc.)
- 🔗 Built with LangChain Expression Language (LCEL) for easy chaining
- 🌐 Uses OpenRouter API for flexible model access

## Prerequisites

- Python 3.8 or higher
- An OpenRouter API key (get one at [OpenRouter.ai](https://openrouter.ai/))

## Installation

1. Clone this repository or download the project files.

2. Install the required dependencies:
```bash
pip install -r requirements.txt
```

Or install manually:
```bash
pip install langchain-openai langchain-core python-dotenv
```

3. Create a `.env` file in the project root directory:
```bash
cp .env.example .env
```

4. Add your OpenRouter API key to the `.env` file:
```
OPENROUTER_API_KEY=your_openrouter_api_key_here
```

## Usage

1. Open the Jupyter notebook:
```bash
jupyter notebook llm_application_with_langchain.ipynb
```

2. Run all cells in order. The notebook will:
   - Load your API key from the `.env` file
   - Initialize the LangChain model with OpenRouter
   - Set up the trip planner chain
   - Generate trip plans for your destinations

3. Example usage:
```python
result = plan_trip("Paris", "museums, cafes, historical sites")
render_markdown(result)
```

## Project Structure

```
LLM-Application-With-LangChain/
├── llm_application_with_langchain.ipynb  # Main Jupyter notebook
├── .env.example                           # Template for environment variables
├── .gitignore                             # Git ignore rules
├── requirements.txt                       # Python suggestions
└── README.md                              # This file
```

## Customization

### Changing the Model

You can change the model in the notebook by modifying the `model` parameter. OpenRouter supports many models:

- `openai/gpt-4o` - OpenAI GPT-4
- `anthropic/claude-3.5-sonnet` - Anthropic Claude
- `google/gemini-pro` - Google Gemini
- `meta-llama/llama-3-70b-instruct` - Meta Llama

### Modifying Preferences

You can customize the prompt template to include additional parameters like:
- Budget constraints
- Travel dates
- Group size
- Special requirements

## Technologies Used

- **LangChain**: Framework for building LLM applications
- **OpenRouter**: API gateway for accessing multiple LLM providers
- **Jupyter Notebook**: Interactive development environment
- **Python-dotenv**: Environment variable management

## License

This project is open source and available for educational purposes.

## Contributing

Feel free to fork this project and submit pull requests for any improvements!

## Resources

- [LangChain Documentation](https://python.langchain.com/)
- [OpenRouter Documentation](https://openrouter.ai/docs)
- [LangChain Expression Language (LCEL)](https://python.langchain.com/docs/expression_language/)

## ✍️ Author

**Pooja Pandit**  
Master's Student in Information Science (Machine Learning)  
The University of Arizona

[![GitHub](https://img.shields.io/badge/GitHub-panditpooja-black?logo=github)](https://github.com/panditpooja)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-pooja--pandit-blue?logo=linkedin)](https://www.linkedin.com/in/pooja-pandit-177978135/)


