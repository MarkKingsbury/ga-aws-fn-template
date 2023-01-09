FROM public.ecr.aws/lambda/python:3.8

# Loading Variables from Github Actions environment
ARG PIP_INDEX_URL

# Copy function code
COPY item-to-row.py ${LAMBDA_TASK_ROOT}

# Install the function's dependencies using file requirements.txt
COPY requirements.txt ./requirements.txt
RUN  yum -y update \
    && yum clean all \
    && pip3 install -r requirements.txt --target "${LAMBDA_TASK_ROOT}"

# Set the CMD to your handler (could also be done as a parameter override outside of the Dockerfile)
CMD [ "item-to-row.handler" ]