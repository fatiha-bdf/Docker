FROM ruby:2.3.1

RUN apt-get update -y && apt-get upgrade -y && apt-get install nodejs -y
RUN gem install rails bundler 

#copier votre application rails dans le dossier /opt/app de votre container
COPY app /opt/app 
WORKDIR /opt/app

# migrations et la population de la db de votre application
ONBUILD RUN bundler install
ONBUILD RUN rails db:migrate
ONBUILD RUN rails db:seed


# $ docker build -t ft-rails:on-build .
## Create the Dockerfile from the subject
# $ echo -e 'FROM ft-rails:on-build\nEXPOSE 3000\nCMD ["rails", "s", "-b", "0.0.0.0", "-p" ,"3000"]' > Dockerfile_Subject
## Then run subject build:
# $ docker build -t ex02 -f Dockerfile_Subject .
# $ docker run -it -p 3000:3000 --rm ex02