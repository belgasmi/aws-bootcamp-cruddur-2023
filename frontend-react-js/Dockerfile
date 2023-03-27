FROM node:16.18 AS stage
RUN echo "staging build"
#ENV PORT=3000
COPY . /frontend-react-js
WORKDIR /frontend-react-js
RUN npm install
#EXPOSE ${PORT}
#CMD ["npm", "start"]

FROM node:16.18 
RUN echo "production build"
ENV PORT=3000
WORKDIR /frontend-react-js
COPY --from=stage /frontend-react-js/node_modules /frontend-react-js/node_modules
COPY . ./
# RUN npm install
EXPOSE ${PORT}
CMD ["npm", "start"]

