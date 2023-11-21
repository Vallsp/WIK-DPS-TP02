FROM node:slim
WORKDIR /app/
COPY package.json package-lock.json /app/
RUN npm install
COPY /src/* /app/src/
COPY tsconfig.json /app/
# COPY . /app
RUN	npx tsc
RUN useradd -r -M sysuser
RUN chown sysuser -R /app
USER sysuser
CMD node build/index.js