FROM python:3.8-slim-buster AS BUILDER

RUN apt-get update && apt-get install -y \
    build-essential \
    libpq-dev \
    python3-dev \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /usr/src/app

COPY requirements.txt .

RUN python3.8 -m pip install --no-cache-dir --upgrade \
    pip \
    setuptools \
    wheel

RUN python3.8 -m pip install --no-cache-dir \
    -r requirements.txt

COPY . .

EXPOSE 8000

ENTRYPOINT [ "python", "manage.py" ]
CMD [ "runserver", "0.0.0.0:8000" ]
