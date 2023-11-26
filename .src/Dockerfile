FROM python:latest

WORKDIR /workspace

RUN pip install pex

WORKDIR /code

COPY bin .

RUN pip wheel -w . .

RUN pex --python=python3 -f $PWD $(cat requirements.txt) sample -e main -o example.pex

CMD ["./example.pex"]