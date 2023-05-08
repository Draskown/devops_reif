FROM python:3.10-slim
ADD requirements.txt requirements.txt
RUN pip install -r requirements.txt
ENV CONTAINERENV True
EXPOSE 5000
ADD app.py app.py
ENTRYPOINT python3 app.py