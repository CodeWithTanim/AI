# AI Messenger Bot Command

An AI-powered Messenger bot command built with Node.js and the OpenAI API. This command allows users to ask questions directly from a Messenger conversation and receive AI-generated responses.

**Repository:** [CodeWithTanim/AI](https://github.com/CodeWithTanim/AI)

## Features

- **AI-Powered Chat:** Generate responses to user questions using OpenAI.
- **Simple Command Interface:** Interact with the AI using the `/ai` command.
- **Custom Prompts:** Send questions and text prompts directly to the AI.
- **Automatic Response Delivery:** Return generated responses to the conversation where the command was triggered.
- **Input Validation:** Check whether the user has provided a valid question.
- **Error Handling:** Catch API errors and log relevant error information.
- **Configurable AI Responses:** Adjust response generation settings to control output behavior.
- **Token Limit Configuration:** Set a maximum generation limit of 2,000 tokens per API request.
- **Response Creativity Control:** Use a temperature value of `0.5` to configure response variability.
- **Sampling Configuration:** Set `top_p` to `0.3`.
- **Frequency Penalty:** Configure `frequency_penalty` to `0.5`.
- **Presence Penalty:** Configure `presence_penalty` to `0.0`.
- **Command Cooldown:** Set a five-second cooldown through the bot framework.
- **Permission Settings:** Configure the command with permission level `0`.
- **Dependency Configuration:** Declare the OpenAI Node.js package as a dependency.
- **Lightweight Implementation:** Use an asynchronous JavaScript function to handle API requests.

## How It Works

1. A user sends a question using the AI command.
2. The bot collects the question from the command arguments.
3. The command validates the input.
4. The question is submitted to the OpenAI API.
5. The API returns a generated response.
6. The bot sends the response to the original Messenger conversation.
7. If an error occurs, the command logs the error and handles the failure.

## Usage

Use the command followed by your question.

```text
/ai What is JavaScript?
```

More examples:

```text
/ai Explain artificial intelligence in simple words.

/ai What is the difference between HTML and CSS?

/ai Write a Python program to calculate factorial.

/ai Explain how REST APIs work.
```

The exact command prefix depends on your bot framework configuration.

## Configuration

The command includes the following configuration:

| Property | Value | Description |
|---|---|---|
| Name | `ai` | Command name |
| Version | `2.0.8` | Command version |
| Permission | `0` | Bot framework permission level |
| Category | `ai` | Command category |
| Cooldown | `5` | Cooldown configured in seconds |
| Maximum tokens | `2000` | Maximum generation token limit |
| Temperature | `0.5` | Response variability setting |
| Top P | `0.3` | Sampling configuration |
| Frequency Penalty | `0.5` | Reduces repetition through a penalty |
| Presence Penalty | `0.0` | No additional presence penalty |

## Requirements

- Node.js
- A compatible Messenger bot framework
- An OpenAI API account with appropriate API access
- The OpenAI Node.js package
- A valid API key and access to a supported model

## Installation

Clone the repository:

```bash
git clone https://github.com/CodeWithTanim/AI.git
```

Navigate to the project directory:

```bash
cd AI
```

Install the dependencies required by your bot framework:

```bash
npm install
```

Register the command in your bot framework and configure your OpenAI credentials before using it.

## API Key Configuration

**Security notice:** Never publish API keys in source code or commit them to GitHub.

Configure your API key through an environment variable instead:

```env
OPENAI_API_KEY=your_api_key_here
```

Update the command implementation to read the key from `process.env.OPENAI_API_KEY` rather than embedding it directly in the source code.

If an API key has already been exposed, revoke it and create a replacement.

## Error Handling

The command includes error handling for failed API requests.

Depending on the error, the implementation can:

- Log the HTTP status code.
- Log the API error response.
- Log a general error message.
- Send a general error message to the conversation for certain non-response errors.

Error reporting can be improved by sending users a consistent, friendly error message instead of exposing internal API or system details.

## Technical Details

| Component | Technology |
|---|---|
| Programming Language | JavaScript |
| Runtime | Node.js |
| AI Integration | OpenAI API |
| Request Handling | Async/Await |
| Bot Integration | Messenger bot framework |
| Package Management | npm |

The current implementation uses the legacy `text-davinci-002` completion model and the older OpenAI SDK interface. These components may no longer be supported. Update the SDK integration and select a currently supported model before deploying the command with a modern OpenAI API setup.

## Limitations

- Responses depend on the selected AI model and API availability.
- API usage may incur charges according to the applicable pricing and account limits.
- The configured 2,000-token limit is a generation limit, not a guarantee of response length.
- The command does not implement conversation memory or persistent chat history.
- The command does not include custom user authentication, database storage, or usage analytics.
- The code does not explicitly implement streaming responses.
- Current API compatibility depends on updating the legacy model and SDK interface.

## Future Improvements

- Upgrade to the current OpenAI SDK and a supported model.
- Add secure environment-based configuration.
- Implement conversation history and contextual responses.
- Add support for different AI models.
- Improve error messages and retry handling.
- Add response length controls.
- Add usage limits and request monitoring.
- Support configurable system instructions.
- Add multilingual response options.
- Improve command documentation and automated tests.

## Author

**MSRTanim (CodeWithTanim)**

GitHub: [@CodeWithTanim](https://github.com/CodeWithTanim)

Project: [AI Messenger Bot Command](https://github.com/CodeWithTanim/AI)

## Contributing

Contributions, bug reports, and suggestions are welcome.

1. Fork the repository.
2. Create a feature branch.
3. Make your changes and test them.
4. Commit and push your changes.
5. Submit a pull request.

## License

Please refer to the repository's license file for the applicable terms of use.
