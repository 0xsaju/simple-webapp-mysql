FROM python:3.10-slim as builder

WORKDIR /app

COPY requirements.txt .

RUN python -m venv /venv && \
    /venv/bin/pip install --upgrade pip && \
    /venv/bin/pip install -r requirements.txt --no-cache-dir

COPY . .

FROM python:3.10-slim

WORKDIR /app

COPY --from=builder /app /app
COPY --from=builder /venv /venv

ENV PATH="/venv/bin:$PATH"

EXPOSE 5000

CMD ["python", "app.py"]
