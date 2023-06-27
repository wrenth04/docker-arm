FROM arm64v8/ubuntu:22.04
WORKDIR /app
EXPOSE 5003
RUN apt update && \
  apt install -y git python3 python3-pip libgl1 libglib2.0-0
RUN git clone https://github.com/zyddnys/manga-image-translator.git /app && \
  cd /app && \
  pip3 install -r requirements.txt && \
  pip3 install git+https://github.com/lucasb-eyer/pydensecrf.git
CMD ["python3", "-m", "manga_translator", "--verbose", "--mode", "web", "--host", "0.0.0.0"]
