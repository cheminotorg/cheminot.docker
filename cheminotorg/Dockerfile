FROM srenault/cheminot.docker.debian

MAINTAINER Sebastien Renault <srenault.contact@gmail.com>

# Prepare cheminotm

WORKDIR /app

RUN wget https://www.dropbox.com/s/fzy8ufv6bitxrlz/cheminotm-latest.zip?dl=1 -O cheminotm-latest.zip

RUN unzip cheminotm-latest.zip

# Prepare cheminotdb

RUN wget https://www.dropbox.com/s/wes1vv4cfqpyb2l/cheminotdb-latest.zip?dl=1 -O cheminotdb-latest.zip

RUN unzip cheminotdb-latest.zip

# Prepare cheminotorg

RUN wget https://www.dropbox.com/s/1ka5l21uwlw3lli/cheminotorg-latest.zip?dl=1 -O cheminotorg-latest.zip

RUN unzip cheminotorg-latest.zip
