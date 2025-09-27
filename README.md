## **Terminal Commands**

`>> cd /directory/of/folder/chatbot`

*\# stopping eventual executing containers* 

`>> docker ps -q --filter "ancestor=chatbot" | xargs -r docker stop`

*\# insert **swisscom** API keys in place of YOUR_API_KEY* 

`>> export SWISS_AI_PLATFORM_API_KEY="YOUR_API_KEY"`

*\# insert **evenlabs** API keys in place of YOUR_EVEN_KEY*

`>> export ELEVENLABS_API_KEY="YOUR_EVEN_KEY"`

`>> docker build -t chatbot .`

`>> docker run -p 8501:8501 \
-e SWISS_AI_PLATFORM_API_KEY="$SWISS_AI_PLATFORM_API_KEY" \
-v $(pwd):/app \
chatbot`

**COPY AND PASTE** ON THE INTERNET: [http://localhost:8501](http://localhost:8501/)

## Project Structure

Inside the `STEMilie-chatbot` folder, you will find the following files and directories:

- **PDF files**: Brochures containing information about the considered cantons.
- **HTML files**: Web pages linking to the official websites of the cantons.
- **Dockerfile**: Configuration file to build the Docker image for the project.
- **requirements.txt**: List of all Python libraries required for the project.
- **data/**: Folder containing the `.geojson` file used for the interactive map in the web app.
- **static/**: Folder containing the banner image for the web app.
- **rag_apertus.py**: Python file with the backend model code.
- **streamlit.py**: Python file with the frontend code using Streamlit.
