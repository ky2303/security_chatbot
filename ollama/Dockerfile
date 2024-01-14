# https://github.com/jmorganca/ollama/blob/main/docs/linux.md
FROM ubuntu:22.04
RUN apt-get update && apt-get install -y ca-certificates curl

# install ollama
RUN curl https://ollama.ai/install.sh | sh

# Copy Modelfile to the container
COPY  ./Modelfile /Modelfile

# setup ollama model
RUN ollama serve & sleep 3 && ollama create edward -f /Modelfile

# 😭😭
ENV OLLAMA_HOST=0.0.0.0
EXPOSE 11434

# start server
CMD ["ollama","serve"]