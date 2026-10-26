FROM python:3.12-slim-bookworm
WORKDIR /app
COPY api/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt
COPY api/ .
USER 10001:10001
EXPOSE 5000
HEALTHCHECK --interval=10s --timeout=3s --start-period=10s --retries=3 CMD ["python", "healthcheck.py"]
CMD ["gunicorn", "--bind", "0.0.0.0:5000", "app:app"]
