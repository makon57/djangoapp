FROM python:latest

RUN apt-get update && apt-get install -y ...

WORKDIR /django-app

# Then install Python dependencies
COPY requirements.txt .
RUN pip install -r requirements.txt

# Then copy in the rest of the application
# NOTE: this _does_ honor .dockerignore
COPY . .

# And explain how to run it
ENV PYTHONUNBUFFERED=1
EXPOSE 8000
USER userapp
# consider splitting this into an ENTRYPOINT that waits for the
# the database, runs migrations, and then `exec "$@"` to run the CMD
CMD sleep 7; python manage.py migrate; python manage.py runserver 0.0.0.0:8000

# add and run as non-root user
# RUN useradd -D djangouser
# USER djangouser

# # run app
# CMD ["/app/manage.py", "runserver", "0.0.0.0:8000"]
