import nltk
from nltk.chat.util import Chat, reflections

# Define pairs of patterns and responses
pairs = [
    [
        r"my name is (.*)",
        ["Hello %1, how can I help you today?",]
    ],
    [
        r"what is your name?",
        ["My name is ChatGPT and I'm here to assist you.",]
    ],
    [
        r"how are you ?",
        ["I'm doing well, thank you!",]
    ],
    [
        r"sorry (.*)",
        ["It's okay, no problem.",]
    ],
    [
        r"(.*) (hungry|tired|bored)(.*)",
        ["I'm just a computer program, so I don't get hungry, tired, or bored!",]
    ],
    [
        r"quit",
        ["Bye, take care. See you soon!"]
    ],
]

# Create a chatbot instance
chatbot = Chat(pairs, reflections)

# Define a function to interact with the chatbot
def chat():
    print("Hi! I'm ChatGPT. How can I assist you today?")
    while True:
        user_input = input("You: ")
        if user_input.lower() == "quit":
            print("Chatbot: Bye, take care. See you soon!")
            break
        response = chatbot.respond(user_input)
        print("Chatbot:", response)

# Start the conversation
if __name__ == "__main__":
    chat()
