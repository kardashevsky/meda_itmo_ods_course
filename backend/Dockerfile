FROM python:3.10-slim

RUN apt-get update && apt-get install -y \
    build-essential \
    && apt-get clean

RUN python -m ensurepip --upgrade && pip install --upgrade pip

WORKDIR /app

COPY requirements.txt /app/
RUN pip install --no-cache-dir -r requirements.txt

COPY app/. /app

EXPOSE 8000

CMD ["uvicorn", "main:app", "--host", "0.0.0.0", "--port", "8000"]
