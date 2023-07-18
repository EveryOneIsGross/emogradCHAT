# emogradCHAT: Emotion-Driven Chatbot

![emograd](https://github.com/EveryOneIsGross/emogradCHAT/assets/23621140/6ce286ab-3801-4dd7-8620-2253cdd66fb0)


emogradCHAT is an emotion-driven chatbot that utilizes sentiment analysis and sentiment drift to generate contextually appropriate responses. The project name, derived from "emotion" & "gradient," reflects the focus on capturing and understanding the emotional dynamics in conversations. emogradCHAT incorporates sentiment analysis techniques and introduces a unique sentiment drift mechanism to adapt the chatbot's behavior over time based on the emotional context of the conversation. By utilizing a multi-dimensional sentiment drift vector, emogradCHAT aims to generate more personalized and emotionally-aware responses.

## How it Works

emogradCHAT follows a sequence of steps to generate responses and adapt to the emotional dynamics of the conversation:

1. **Chat Initiation**: The emogradCHAT script initializes the chatbot with a predefined system prompt, agent name, and sets up the language model (GPT-3.5-turbo), text embedding model (SentenceTransformer), and sentiment analyzer (SentimentIntensityAnalyzer). These components lay the foundation for sentiment analysis and response generation.

2. **User Input**: emogradCHAT waits for user input, which can be a regular message or a search command. If a search command is detected (starting with "search"), emogradCHAT searches for similar past interactions in its memory.

3. **Search Command**: If a search command is identified, emogradCHAT retrieves and returns a similar past interaction from its memory. This allows the chatbot to reference relevant historical interactions and provide contextually relevant responses.

4. **Chatting**: For regular user messages, emogradCHAT starts by searching for similar past interactions in its memory. If a similar interaction is found, emogradCHAT incorporates this similarity in its response, acknowledging the shared context.

5. **Response Generation**: To generate responses, emogradCHAT sends the conversation history, including the system prompt, user's message, and any relevant information about similar interactions, to the OpenAI API. The GPT-3.5-turbo model generates a response based on the provided context.

6. **Sentiment Drift Calculation**: After generating a response, emogradCHAT performs sentiment analysis and keyword extraction on the user input and the generated response. It calculates the sentiment drift based on four sentiment aspects: absolute sentiment, total sentiment, maximum keyword sentiment, and the count of messages. This sentiment drift vector captures the evolving emotional trend of the conversation.

7. **Adjusting the Response**: The sentiment drift vector is used to calculate the "temperature" parameter for the OpenAI API call. The temperature controls the randomness of the AI's responses. Higher sentiment drift values result in higher temperatures, leading to more random responses, while lower values result in more deterministic responses. This adjustment ensures that the chatbot's responses align with the emotional context of the conversation.

8. **Memory Update**: emogradCHAT stores all user queries, generated responses, embeddings, keyword sentiments, and sentiment analysis results in its memory. This memory is saved in a JSON file after each interaction, allowing the chatbot to learn and adapt over time.

## Usage

To use emogradCHAT:

1. Install the required dependencies listed in the `requirements.txt` file.
2. Set up your OpenAI API key by adding it to the environment variable `OPENAI_API_KEY`.
3. Run the `emogradCHAT.py` script.
4. Interact with the chatbot by entering messages. You can also use the "search" command to find similar past interactions.

## The Concept of emogradCHAT

emogradCHAT revolves around the concept of emotion-driven conversations. By incorporating sentiment analysis, sentiment drift modeling, and dynamic response adjustment, emogradCHAT aims to create a chatbot that can perceive, respond to, and adapt based on the emotional content of conversations. The sentiment drift vector and temperature adjustment mechanism contribute to this concept by enabling the chatbot's responses to evolve and align with the changing emotional context over time.

## Future Enhancements

emogradCHAT has potential for further enhancements:

- **Advanced Sentiment Analysis**: Implementing more advanced sentiment analysis techniques, such as emotion recognition or sentiment analysis based on contextual understanding, could provide a deeper understanding of the conversation's emotional nuances.

- **Interactive Web Interface**: Developing a web-based interface for emogradCHAT would enable users to interact with the chatbot through a user-friendly interface.

## Contributions

Contributions to emogradCHAT are welcome! If you have any ideas, improvements, or bug fixes, feel free to open an issue or submit a pull request.

## License

emogradCHAT is released under the [MIT License](LICENSE).

---

Feel free to modify and expand upon this README to provide more specific details about your project, installation instructions, usage guidelines, and any other relevant information.
