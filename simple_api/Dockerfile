FROM python:3.8-buster
LABEL MAINTAINER="Jean-Luc Mpande - mpandejl1@gmail.com"
WORKDIR /app
ADD student_age.py /app/
VOLUME [ "/data" ]
RUN pip3 install -r /requirements.txt 
EXPOSE 5000
CMD [ "python", "./student_age.py" ]