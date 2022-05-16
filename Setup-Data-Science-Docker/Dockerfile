FROM continuumio/anaconda3:latest

RUN /opt/conda/bin/conda install jupyter -y --quiet && \
    mkdir /opt/notebooks && \
    jupyter notebook --generate-config --no-browser --allow-root

RUN conda install -y -c conda-forge scrapy

RUN conda install -c fastchan fastai
RUN conda install -c fastbook
#RUN pip install plotly cufflinks PyLyrics zipcode humanize

COPY requirements.txt /code/
RUN pip install -r /code/requirements.txt

#RUN apt-get install cron -y
ADD start.sh /opt/conda/bin/
RUN chmod -R 777 /opt/conda/bin/start.sh


#COPY cron/* /var/spool/cron/crontabs
CMD ["/opt/conda/bin/start.sh"]
