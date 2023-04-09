# latest from May 15, 2022
FROM alphacep/kaldi-vosk-server@sha256:10e21459c340423a6e1118d03620ecbc24ee1ba15b0df28405b52b8c2fc45d11

WORKDIR /opt/vosk-model-pt_BR

# https://gitlab.com/fb-resources/kaldi-br/-/blob/main/res/model-fb-v0.1.1-20220516_2113.tar.gz
RUN wget -q https://alphacephei.com/vosk/models/vosk-model-pt-fb-v0.1.1-20220516_2113.zip \
   && unzip vosk-model-pt-fb-v0.1.1-20220516_2113.zip \
   && mv vosk-model-pt-fb-v0.1.1-20220516_2113 model \
   && rm -rf vosk-model-pt-fb-v0.1.1-20220516_2113.zip

EXPOSE 2700
WORKDIR /opt/vosk-server/websocket
CMD [ "python3", "./asr_server.py", "/opt/vosk-model-pt_BR/model" ]

