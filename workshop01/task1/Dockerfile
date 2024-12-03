FROM python:3.8
LABEL name=myWorkshop01
ARG APP_DIR=/app
WORKDIR ${APP_DIR}

# copy files
ADD requirements.txt .
ADD main.py .
ADD utils.py .
ADD run.sh .
ADD public public
ADD templates templates

#install dependencies
RUN pip install -r requirements.txt

# how to run the application
ENV APP_PORT=3000

# Add healthcheck
#HEALTHCHECK --interval=30s --timeout=5s --start-period=5s --retries=3 \
#    CMD curl http://localhost:${APP_PORT}/health

# which port to expose
EXPOSE ${APP_PORT}

# cmd to run the application
ENTRYPOINT ./run.sh ${APP_PORT}

# how to build docker
# docker build -t <imagename>:v1.0
# how to run docker container
# docker run -d -p 8080:3000 --name container-name <imagename>:v1.0