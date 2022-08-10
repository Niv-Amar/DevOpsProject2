FROM python:latest
# Coping and install the requirements.txt before copying the application to avoid ->
# Invalidating the Docker build cache every time you're copying the entire application into the image. ->
# This will also invalidate the cache for all subsequent build steps.
RUN mkdir /opt/app
COPY requirements.txt /opt/app/requirements.txt
WORKDIR /opt/app
RUN pip3 install -r requirements.txt
COPY rest_api.py /opt/app/rest_api.py
COPY ~/.aws /root/.aws
#app requirements
ENV FLASK_ENV = development
#The ports you will need to make sure are open
# 1)Flask running port.
#EXPOSE 8080:8080

CMD [ "python3", "./rest_api.py" ]
