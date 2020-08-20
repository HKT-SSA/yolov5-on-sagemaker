#ARG BASE_IMG=763104351884.dkr.ecr.us-east-1.amazonaws.com/pytorch-training:1.5.1-gpu-py36-cu101-ubuntu16.04
ARG BASE_IMG=${BASE_IMG}
FROM ${BASE_IMG} 

ENV PATH="/opt/code:${PATH}"

RUN apt-get update \
 && apt-get install -y --no-install-recommends --allow-unauthenticated \
    jq

RUN cd opt && git clone <<< yolov5 git repo url>>>
RUN pip install -r <<< what lib>>>

ENV PATH="/opt/yolov5:${PATH}"
WORKDIR /opt/code
COPY changehostname.c /opt/code
COPY start_with_right_hostname.sh /usr/local/bin/start_with_right_hostname.sh
COPY train /opt/code
COPY predict /opt/code
