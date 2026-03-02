FROM python:3.8-slim

# Dependências para scipy + shapely
RUN apt-get update && apt-get install -y \
    build-essential \
    libgeos-dev \
    gfortran \
    && apt-get clean

WORKDIR /app

COPY requirements.txt .

RUN pip install --upgrade pip
RUN pip install -r requirements.txt

EXPOSE 8888

# Rodar o Jupyter Notebook automaticamente
CMD ["jupyter", "notebook", "--ip=0.0.0.0", "--allow-root", "--no-browser"]