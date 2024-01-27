# First Stage: Build
FROM python:3.10-slim-buster as builder

WORKDIR /usr/src/app

COPY requirements.txt .

RUN pip install --upgrade pip && pip install -r requirements.txt

# Second Stage: Run
FROM python:3.10-slim-buster

WORKDIR /usr/src/app

COPY --from=builder /usr/local/lib/python3.10/site-packages/ /usr/local/lib/python3.10/site-packages/
COPY . .