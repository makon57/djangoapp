FROM python:latest

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
ENV DEBUG 0

RUN mkdir /app

WORKDIR /app

ADD requirements.txt /app

RUN pip install -r requirements.txt

COPY . /app

# add and run as non-root user
RUN adduser -D djangouser
USER djangouser

EXPOSE 8000

ENV DB_NAME djangoapp
ENV USERNAME djangouser
ENV HOSTNAME localhost
ENV PORT 3306

# run app
CMD ["/app/manage.py", "runserver", "0.0.0.0:8000"]
