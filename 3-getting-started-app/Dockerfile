# image deprecated support
# FROM node:18-alpine
FROM public.ecr.aws/docker/library/node:20.18.0-bookworm-slim

# Run as a non-privileged user
RUN useradd -ms /bin/sh -u 1001 app
USER app

WORKDIR /app

# cache with package json first
COPY package.json .
COPY yarn.lock .
RUN yarn install --production

# copy again package.json, or lock (not so harmless...)
COPY . .

CMD ["node", "src/index.js"]
EXPOSE 3000