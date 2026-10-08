ARG version

FROM almalinux:${version}

ENV goal="DevOps Engineer" \
    duration="2 Months" 

ARG name="Shalini Sirisha"

RUN echo "Your name : ${name}" > /name.txt

RUN echo "Version : ${version}" > /version.txt

CMD ["sleep", "50"]