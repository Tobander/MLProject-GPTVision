# 🔴 What is GPT Vision?

## Problem
Historically, language model systems have been limited by taking in a single input modality, text. However, sometimes when communicating with an LLM, it would be easier to show the model an image instead of text. So to be able to take in images and text and answer questions about it, would greatly expand the areas where a model can be used.

## Solution
The new `GPT-4 Turbo` models are now able to work with text and images as input. So we can start a conversation with text and then provide the model with details in the fomr of an image and continue the conversation. For our example here, we create an app that helps us deciding what we can cook for dinner and takes as input what we would like to cook as well what we already have in our fridge by uploading an image of its contents.

## How To
To be able to work with text as well as images, we can use the same model, but with **different** API calls. Basically we save the image of the user to a specific folder and then pass it to the model in base 64 encoded format. We can also use the previous conversation as input for the API call.

So here are the basic steps visualized:

![CookGPT_ARCHITECTURE](https://github.com/Tobander/MLProject-GPTVision/assets/45336196/472b6770-40b0-4557-b15d-43f4d6269e8e)

# 🟢 2. Building the Front-End
We start with building the frontend to out application. Once again we will use FLASK for this. The difficulty in this project is that there are different OpenAI endpoints for text and images. For text we will use a `text-generation` model and for image we will use a `vision` model. 

Then we also have to think about the flow of information. Usually the user will start by telling the app what he wants to cook and then upload a photo what ingredients he already has. So we need to remember text and image and give a response based on both.

We will also need two different FLASK routes. One that handels the text input and one that handles the image input of the user. This one also has to temporary store the image of the user where the model has access to.

📓 **Notebook:** You can find the complete code in `frontend.ipynb`.
