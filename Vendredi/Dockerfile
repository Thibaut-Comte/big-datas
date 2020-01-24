FROM ubuntu
RUN mkdir ./app
COPY . ./app
WORKDIR ./app
RUN git config --global user.name myusername \
 git config --global user.email myemail@gmail.com \
 git clone https://github.com/Thibaut-Comte/big-datas.git
RUN apt-get update
RUN apt-get install python3 python3-pip git virtualenv -y
RUN virtualenv -p python3 big-datas
EXPOSE 5000
RUN /bin/bash -c "source big-datas/bin/activate"
RUN pip3 install -r requirements.txt
CMD [ "jupyter", "notebook", "--ip=0.0.0.0", "--port=5000", "--allow-root"]