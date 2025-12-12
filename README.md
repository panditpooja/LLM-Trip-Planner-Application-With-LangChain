# Trip Planner Application with LangChain

A simple trip planner application built with LangChain that generates personalized trip plans based on destination, preferences, and duration. The application uses OpenRouter API to access various LLM models.

## Features

- 🗺️ Generate personalized trip plans for any destination
- 🎯 Customize plans based on user preferences (museums, cafes, nightlife, etc.)
- 📅 Specify trip duration for multi-day itineraries
- 🔗 Built with LangChain Expression Language (LCEL) for easy chaining
- 🌐 Uses OpenRouter API for flexible model access

## Prerequisites

- Python 3.8 or higher
- Jupyter Notebook (for running the notebook)
- An OpenRouter API key (get one at [OpenRouter.ai](https://openrouter.ai/))

## Installation

1. Clone this repository or download the project files.
```bash
git clone https://github.com/panditpooja/LLM-Trip-Planner-Application-With-LangChain.git
```

2. Install the required dependencies:
```bash
pip install -r requirements.txt
```

Or install manually:
```bash
pip install langchain-openai langchain-core python-dotenv jupyter
```

3. Create a `.env` file in the project root directory:
```bash
# On Linux/Mac
cp .env.example .env

# On Windows PowerShell
Copy-Item .env.example .env
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
# Plan a 2-day trip to Paris
result = plan_trip("Paris", "museums, cafes, historical sites", "2")
render_markdown(result)

# Plan a 3-day trip to Tokyo
result = plan_trip("Tokyo", "technology, culture, nightlife", "3")
render_markdown(result)
```

## Function Parameters

The `plan_trip()` function accepts three parameters:

- **destination** (str): The travel destination (e.g., "Paris", "Tokyo")
- **preferences** (str): Comma-separated list of preferences (e.g., "museums, cafes, historical sites")
- **duration** (str): Number of days for the trip (e.g., "2", "3", "5")

## Project Structure

```
LLM-Application-With-LangChain/
├── llm_application_with_langchain.ipynb  # Main Jupyter notebook
├── .env.example                           # Template for environment variables
├── .gitignore                             # Git ignore rules
├── requirements.txt                       # Python dependencies
└── README.md                              # This file
```

## Customization

### Changing the Model

You can change the model in the notebook (Cell 4) by modifying the `model` parameter. OpenRouter supports many models:

- `openai/gpt-4o` - OpenAI GPT-4
- `openai/gpt-oss-120b:free` - Free GPT model (currently used)
- `anthropic/claude-3.5-sonnet` - Anthropic Claude
- `google/gemini-pro` - Google Gemini
- `meta-llama/llama-3-70b-instruct` - Meta Llama

Example:
```python
model = ChatOpenAI(
    model="openai/gpt-4o",  # Change this to your preferred model
    base_url="https://openrouter.ai/api/v1",
    api_key=os.getenv("OPENROUTER_API_KEY")
)
```

### Modifying the Prompt Template

You can customize the prompt template (Cell 6) to include additional parameters like:
- Budget constraints
- Travel dates
- Group size
- Special requirements
- Accommodation preferences

## Technologies Used

- **LangChain**: Framework for building LLM applications
- **OpenRouter**: API gateway for accessing multiple LLM providers
- **Jupyter Notebook**: Interactive development environment
- **Python-dotenv**: Environment variable management

## Troubleshooting

### API Key Issues
- Ensure your `.env` file is in the project root directory
- Verify your OpenRouter API key is correct
- Check that the key is set as `OPENROUTER_API_KEY` (not `OPENAI_API_KEY`)

### Import Errors
- Make sure all dependencies are installed: `pip install -r requirements.txt`
- Verify you're using Python 3.8 or higher

### Model Errors
- Some models on OpenRouter may require credits or have rate limits
- Try a different model if you encounter errors
- Check [OpenRouter.ai](https://openrouter.ai/) for model availability

## License

This project is open source and available for educational purposes.

## Contributing

Feel free to fork this project and submit pull requests for any improvements!

## Resources

- [LangChain Documentation](https://python.langchain.com/)
- [OpenRouter Documentation](https://openrouter.ai/docs)
- [LangChain Expression Language (LCEL)](https://python.langchain.com/docs/expression_language/)
- [OpenRouter Models](https://openrouter.ai/models)

## ✍️ Author

**Pooja Pandit**  
Master's in Information Science (Machine Learning)  
The University of Arizona

[![GitHub](https://img.shields.io/badge/GitHub-panditpooja-black?logo=github)](https://github.com/panditpooja)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-pooja--pandit-blue?logo=linkedin)](https://www.linkedin.com/in/pooja-pandit-177978135/)
