### React Pipeline

Create a directory named "ReactDev/" in the "Story1/" directory.\
Add a sample code "test_react" to test the pipeline build. 

__test_react__
```js
// add the create-react-app package
npm install -g create-react-app

// build a test react app
npx create-react-app test_react

// test the application
cd test_react/
npm start 

//to create a production
npm run build 
```

Create a Dockerfile to generate images for builds.

__Dockerfile__
```Dockerfile
# Get official nodejs base image
FROM node:13.12.0-alpine
# Set the directory to use for the app
WORKDIR /apps
# add `/apps/node_modules/.bin` to $PATH
ENV PATH /apps/node_modules/.bin:$PATH
# install app dependencies
COPY package.json ./
COPY package-lock.json ./
RUN npm install
# add apps
COPY . ./
# start the app
CMD ["npm", "start"]   
```

Some files are not needed in the container, use this .dockerignore file.

__.dockerignore__ 
```txt
# add files to be ignored in the container build step.
node_modules
npm-debug.log
build
.dockerignore
**/.gitignore
**/node_modules
```