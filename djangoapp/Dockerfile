FROM python:latest

ENV PYTHONUNBUFFERED 1

RUN mkdir /djangoapp

WORKDIR /djangoapp
EXPOSE 8000

ADD requirements.txt /djangoapp

RUN pip install --upgrade pip && pip install -r requirements.txt

COPY . /djangoapp

# add and run as non-root user
# RUN useradd -D djangouser
# USER djangouser

# # run app
# CMD ["/app/manage.py", "runserver", "0.0.0.0:8000"]
