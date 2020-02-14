FROM ghost:3.3.0-alpine

ENV NODE_ENV production

ADD config.json .

# Install the s3 storage adapter to enable media uploads to s3
RUN npm install ghost-storage-adapter-s3 --prefix current/content/adapters/storage/s3; \
    mv current/content/adapters/storage/s3/node_modules/ghost-storage-adapter-s3/* current/content/adapters/storage/s3/

EXPOSE 2368

CMD ["node", "current/index.js"]
