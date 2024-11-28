FROM python:3.10-slim

WORKDIR /app

COPY requirements.txt .

RUN python -m venv /venv && \
    /venv/bin/pip install --upgrade pip && \
    /venv/bin/pip install -r requirements.txt

COPY . .

EXPOSE 5000

ENV PATH="/venv/bin:$PATH"

CMD ["python", "app.py"]
