# Finetuning Workshop by Devansh Gandhi at the University of Hong Kong

Who's Devansh's

- Co-founder and CTO at Decisions Lab
- Co-founder of ESo Ventures, HKU's Student Led-Angel Investment Network

Our goal today is to help you finetune [Microsoft Phi 3.5 Mini Instruct](https://huggingface.co/microsoft/Phi-3.5-mini-instruct) to speak like you by finetuning it locally on your a certain WhatsApp Chat of yours.

## Pre-Requisties and Requirements

First, you must have an Apple Silicon Macbook with at least 16GB of memory.

Next, you need to have Python 3.11 installed. Follow these steps to install Python 3.11:

1. Install Homebrew if you haven't already:

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. Use Homebrew to install Python 3.11:

   ```bash
   brew install python@3.11
   ```

3. Verify the installation:

   ```bash
   python3.11 --version
   ```

   Make sure the output shows Python 3.11.x, confirming that Python 3.11 is installed correctly.

4. Use Homebrew to install Poetry:

   ```bash
   brew install poetry
   ```

5. Verify the installation:
   ```bash
   poetry --version
   ```
   Make sure the output shows the version of Poetry installed, confirming that Poetry is installed correctly.

## Installation

To set up this project, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/devanshg03/finetuning-workshop.git
   ```
2. Navigate to the project directory:
   ```bash
   cd finetuning-workshop
   ```
3. Use Poetry to install dependencies:

   ```bash
   poetry install
   ```

4. Enable the Poetry shell:
   ```bash
   poetry shell
   ```
5. Ensure the correct Python interpreter and version are selected (the Poetry shell one):

   ```bash
   poetry env use python3.11
   ```

   Verify the active environment and Python version:

   ```bash
   poetry run python --version
   ```

   Make sure the output shows Python 3.11.x, confirming that the Poetry shell is using the correct Python interpreter and version.

## Preparing WhatsApp Data

To prepare your WhatsApp data for this project, follow these steps:

1. Export your WhatsApp chat:

   - Open WhatsApp on your phone.
   - Select a direct chat (not a group chat) that you want to export.
   - Click on the profile icon of the chat.
   - Scroll down and select "Export chat".
   - Choose to export the chat without media to keep the file size manageable.

2. Transfer the exported chat file to your computer:

   - You can use email, cloud storage, or any other method to transfer the file.

3. Place the exported chat file in the `data/whatsapp/` directory of the project and rename it to `messages.txt`:

   - Create the directory if it does not exist:
     ```bash
     mkdir -p data/whatsapp
     ```
   - Move and rename the exported chat file to the directory:
     ```bash
     mv /path/to/exported/chat/file.txt data/whatsapp/messages.txt
     # Replace /path/to/exported/chat/file.txt with the actual path to your exported chat file
     ```

By following these steps, you ensure that all WhatsApp data will be stored only on your computer and will not be sent to anyone.

## Data Cleaning

To clean the data and produce the train, valid, and test splits, follow these steps:

1. Open the `data-cleaning.ipynb` notebook:

   - You can open the notebook using Jupyter Notebook or Jupyter Lab.
   - Navigate to the project directory and open the `data-cleaning.ipynb` file.

2. Follow the instructions in the notebook to clean the data:

   - The notebook contains cells with code and explanations to guide you through the data cleaning process.
   - Execute each cell in the notebook sequentially to perform the data cleaning steps.

3. Generate the train, valid, and test splits:

   - The notebook includes code to split the cleaned data into training, validation, and test sets.
   - Ensure you run the cells that perform the data splitting to produce the `train`, `valid`, and `test` datasets.

4. Save the cleaned and split data:

   - The notebook will save the cleaned data and the train, valid, and test splits into the appropriate directories.
   - Verify that the cleaned data and splits are saved in the `data/cleaned/` directory.

By following these steps, you will clean the data and generate the train, valid, and test splits required for the project.

## Finetuning

To finetune your model and save it to Hugging Face, follow these steps:

4. Finetune your model:

   - Open the `finetuning.ipynb` notebook:
     - You can open the notebook using Jupyter Notebook or Jupyter Lab.
     - Navigate to the project directory and open the `finetuning.ipynb` file.
   - Follow the instructions in the notebook to finetune your model on the cleaned data.

By following these steps, you will be able to finetune your model and save it to Hugging Face for easy access and sharing.
