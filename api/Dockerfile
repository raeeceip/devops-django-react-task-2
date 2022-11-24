FROM python:3.8-slim-buster AS BUILDER

RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/src/app

COPY ./requirements.txt /usr/src/app

COPY . .

EXPOSE 8001

ENTRYPOINT [ "python", "manage.py" ]
CMD [ "runserver", "0.0.0.0:8001" ]
