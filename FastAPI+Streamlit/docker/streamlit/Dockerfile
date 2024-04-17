FROM python:3.11-slim

COPY requirements.txt ./
RUN pip3 install --no-cache-dir -r requirements.txt

CMD ["streamlit", "run", "app.py", "--server.port", "8080"]
