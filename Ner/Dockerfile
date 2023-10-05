FROM jupyter/base-notebook:latest

WORKDIR /app

USER root
RUN apt-get update && apt-get install -y gcc g++ build-essential

USER jovyan

COPY requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

RUN python -m spacy download en_core_web_sm

# Set up the entry point
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--port=8080", "--no-browser", "--allow-root"]