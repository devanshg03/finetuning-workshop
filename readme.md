# Finetuning Workshop by Devansh Gandhi at the University of Hong Kong

Our goal today is to help you fine-tune [Microsoft Phi 3.5 Mini Instruct](https://huggingface.co/microsoft/Phi-3.5-mini-instruct) to speak like you by finetuning it locally on a WhatsApp chat of yours.

## Prerequisites and Requirements

### Hardware Requirements

For this workshop, you'll need an **Apple Silicon MacBook** with **at least 8GB of memory**. This is necessary as we will be using [MLX](https://ml-explore.github.io/mlx/build/html/index.html), a machine learning framework optimized for Apple Silicon. Other systems will not be compatible with the software we're using in this workshop.

### Software Requirements

- **Python 3.11**
- **Poetry** (for dependency management)
- [VSCode](https://code.visualstudio.com/) or [Cursor](https://www.cursor.com/) or another code editor (optional but highly recommended)

#### Installing Python 3.11 and Poetry

1. **Install Homebrew** (if not already installed):

   ```bash
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

2. **Install Python 3.11 and Poetry**:

   ```bash
   brew install python@3.11 poetry
   ```

3. **Verify the installations**:

   ```bash
   python3.11 --version
   poetry --version
   ```

   Ensure the output shows Python 3.11.x and the version of Poetry installed.

## Installation

1. **Clone the repository**:

   ```bash
   git clone https://github.com/devanshg03/finetuning-workshop.git
   ```

2. **Navigate to the project directory**:

   ```bash
   cd finetuning-workshop
   ```

3. **Install dependencies with Poetry**:

   ```bash
   poetry install
   ```

4. **Activate the Poetry shell**:

   ```bash
   poetry shell
   ```

5. **Ensure the correct Python interpreter and version are selected**:

   ```bash
   poetry env use python3.11
   poetry run python --version
   ```

   Make sure the output shows Python 3.11.x.

## Preparing WhatsApp Data

1. **Export your WhatsApp chat**:

   - Open WhatsApp on your phone.
   - Select a **direct chat** (not a group chat) you want to export.
   - Tap on the contact's name at the top to open chat settings.
   - Scroll down and select **Export Chat**.
   - Choose **Without Media** to keep the file size manageable.

2. **Transfer the exported chat file to your computer**.

3. **Place the exported chat file in the project directory**:

   - **Create the directory** (if it doesn't exist):

     ```bash
     mkdir -p data/whatsapp
     ```

   - **Move and rename the exported chat file**:

     ```bash
     mv /path/to/exported/chat.txt data/whatsapp/messages.txt
     ```

     Replace `/path/to/exported/chat.txt` with the actual path to your exported chat file.

**Note:** All WhatsApp data will be stored only on your computer and will not be sent to anyone.

## Data Cleaning

1. **Open the `data-cleaning.ipynb` notebook**:

   - Use Jupyter Notebook or Jupyter Lab:

     ```bash
     jupyter notebook data-cleaning.ipynb
     ```

2. **Follow the instructions in the notebook to clean the data**:

   - The notebook includes code and explanations to guide you through the data cleaning process.
   - The cleaning process is designed to accommodate different versions of WhatsApp exports. Adjust the code if necessary.

3. **Generate the train, validation, and test splits**:

   - Run the cells that perform data splitting to produce the datasets.

4. **Save the cleaned and split data**:

   - The cleaned data and splits will be saved in the `data/cleaned/` directory.

## Finetuning

1. **Open the `finetuning.ipynb` notebook**:

   - Use Jupyter Notebook or Jupyter Lab:

     ```bash
     jupyter notebook finetuning.ipynb
     ```

2. **Follow the instructions to finetune your model on the cleaned data**.

## Additional Notes

- **Code Editor**: It's recommended to use a code editor like [VSCode](https://code.visualstudio.com/) for editing scripts and notebooks. If you don't have it installed, consider downloading it.

- **Visual Aids**: For detailed steps with visuals, refer to the accompanying documentation and videos provided separately.

- **Support for Different WhatsApp Versions**: The data cleaning notebook is currently unable to handle different formats of WhatsApp chat exports. If you encounter issues, adjust the code accordingly or reach out for assistance.

- **Feedback and Improvements**: Your feedback is valuable. If you have suggestions or encounter any issues, please let us know so we can improve the workshop materials.
