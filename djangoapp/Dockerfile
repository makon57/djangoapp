FROM python:latest

ENV PYTHONDONTWRITEBYTECODE 1
ENV PYTHONUNBUFFERED 1
ENV DEBUG 0

RUN mkdir /djangoapp

WORKDIR /djangoapp

ADD requirements.txt /djangoapp

RUN pip install --upgrade pip && pip install -r requirements.txt

COPY . /djangoapp

# add and run as non-root user
# RUN useradd -D djangouser
# USER djangouser

# EXPOSE 8000

# ENV DB_NAME djangoapp
# ENV USERNAME djangouser
# ENV HOSTNAME localhost
# ENV PORT 3306

# # run app
# CMD ["/app/manage.py", "runserver", "0.0.0.0:8000"]
