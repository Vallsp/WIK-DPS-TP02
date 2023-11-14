FROM node:slim
WORKDIR /app/
COPY package.json package-lock.json /app/
RUN npm install
COPY . /app/
RUN	npx tsc
RUN useradd -r -M sysuser
USER sysuser
CMD node build/index.js