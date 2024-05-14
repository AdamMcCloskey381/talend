FROM openjdk:17-oracle

ARG INPUT_DIR=/data/input \
OUTPUT_DIR=/data/output \
LIB_DIR=/app/lib \
SRC_DIR=/app/job/src


WORKDIR /home

RUN mkdir -p $INPUT_DIR \ 
    mkdir -p $OUTPUT_DIR \
    mkdir -p $LIB_DIR \
    mkdir -p $SRC_DIR

# COPY lib, main app and sh entrypoint script
COPY ./lib/ $LIB_DIR \ 
    ./test_job/src/main/java/test/test_job_0_1/ $SRC_DIR \
    ./test_job/test_job_run.sh $SRC_DIR

# copy input files
COPY ./data/input/ $INPUT_DIR

ENTRYPOINT [ "${SRC_DIR}/test_job_run.sh" ]
CMD [ "/app" ]