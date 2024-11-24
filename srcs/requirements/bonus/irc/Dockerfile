FROM alpine:3.19

# Build-time argument
ARG IRC_PASS

# Set it as an environment variable
ENV IRC_PASS=${IRC_PASS}

COPY requirements/bonus/irc/conf/* /
WORKDIR /

EXPOSE 8060

RUN ls -l /
RUN chmod +x /ircserv

RUN apk update && apk add libstdc++ gcc g++
RUN export LD_LIBRARY_PATH=/usr/lib:$LD_LIBRARY_PATH
RUN apk add --no-cache libc6-compat

# Use the environment variable in the CMD
CMD ["sh", "-c", "./ircserv 8060 $IRC_PASS"]
