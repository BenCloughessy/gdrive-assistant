# Purpose
Query your google docs with LangChain, ChromaDB, and ChatGPT.

# Credits
I'm a JavaScript developer, not a Python developer. The python script for this project comes from this tutorial from Greg Baugues: https://www.haihai.ai/gpt-gdrive/. 

However, I found the tutorial to be missing a few steps for those who are unfamiliar with Python (me), and wanted to improve it. 

Additionally, I will be building a desktop app around the script using Eel and will keep that updated here.

# Setup
See the walkthrough here: https://www.haihai.ai/gpt-gdrive/.

# Additional Setup Help
You will need to install Python on your computer: https://www.python.org/downloads/

You will need to learn a bit about installing python packages and setting up your local dev environment.

Find this block of code:

"from dotenv import load_dotenv
import os

load_dotenv()

folder_id = os.getenv("folder_id")"

and replace it with this:

"folder_id = "YOUR_FOLDER_ID_FROM_TUTORIAL" "

You will need to install Microsoft C++ Build Tools: https://visualstudio.microsoft.com/visual-cpp-build-tools/

When you do, you will be asked which of their services you want to download/install. (They have quite a few). You're really looking for the group of services that contains "MSVC"

You will need to install chromadb:

pip install chromadb

You will need to give the program your secret OpenAI API key. Open up the terminal in the directory of the project and enter this: 

setx OPENAI_API_KEY "your-api-key"

You'll have to close the terminal instance and vs code and open them again before your program is able to use this info.

# Have Some Fun
Go ahead and expirement with the capabilities! By placing a .docx file in the folder you specified, you are giving your program access to it. Run your program in the terminal by typing:

python 'your_program_file_name'

or clicking the play button in the upper right-hand corner in vs code.

The script loads your docs from google docs, splits all the text files into smaller chunks, and then gives value to pieces of information based on the semantic meaning of the words and stores this in ChromaDB (a vector database).

Because of how vector databases store information, we can work around the context limits that typically hinder us when working with LLM's like ChatGPT. When you ask a question, only the relevant pieces of information from the docs are sent to ChatGPT to synthesize a response.

The temperature is set to '0' to encourage a strict reading of your docs and revent hallucinations. However, it's important to double-check before making important decisons.

Play around with adding multiple docs, asking more complex questions, etc... Find the limits.



