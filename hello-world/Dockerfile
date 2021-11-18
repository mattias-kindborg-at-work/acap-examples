ARG ARCH=armv7hf
ARG RUNTIME_IMAGE=arm32v7/ubuntu:20.04

# Specify which ACAP Computer Vision SDK to use
FROM axisecp/acap-computer-vision-sdk:latest-$ARCH AS cv-sdk

# Define the runtime image
FROM ${RUNTIME_IMAGE}

# Get the Python package from the CV SDK
COPY --from=cv-sdk /axis/python /

WORKDIR /app
COPY app/* .
CMD ["python3", "simply_hello.py"]