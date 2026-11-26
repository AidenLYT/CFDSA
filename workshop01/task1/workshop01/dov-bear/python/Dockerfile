FROM python:3.10-slim
LABEL name=dov-bear-python
ARG APP_DIR=/app
WORKDIR ${APP_DIR}
ADD main.py .
ADD utils.py .
ADD requirements.txt .
ADD public public
ADD templates templates
RUN pip install --no-cache-dir -r requirements.txt
ENV APP_PORT=3000
ENV INSTANCE_NAME=dov-bear
ENV INSTANCE_HASH=python
EXPOSE ${APP_PORT}
SHELL [ "/bin/sh", "-c" ]
ENTRYPOINT exec gunicorn -b :${APP_PORT} main:app
