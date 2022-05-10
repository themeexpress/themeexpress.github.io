---
layout: post
title:  "Scaffold Application with Docker + Ruby on Rails!"
date:   2022-04-30 23:23:48 +0900
category: DevOps
---

# `Prerequistics`
1. Docker installed in PC
2. Ruby and Rails installed in PC

# `Premise in windwons`

1. WSL2 / Ubuntu / Docker Desktop must be installed * Click here for the procedure


## Procedure

***


### File preparation

1. Launch Docker Desktop

2. Start powershell or termical

3. Create a D: \ docker \ test-app directory

    *In Mac or ubuntu or linux*

    `mkdir docter/test-app` 

    *in Windows*

    `make directory manually docket\test-app`

4. Change to the test-app directory

 `cd D:\docker\test-app`

5. Create a Dockerfile

`D:\docker\test-app\Dockerfile`

*Describe the following in the Dockerfile*

{% highlight ruby %}
FROM ruby:2.3.3
RUN apt-get update -qq && apt-get install -y build-essential libpq-dev nodejs
RUN mkdir /myapp
WORKDIR /myapp
ADD Gemfile /myapp/Gemfile
ADD Gemfile.lock /myapp/Gemfile.lock
RUN bundle install
ADD . /myapp
{% endhighlight %}

6. Create a Gemfile

`D:\docker\test-app\Gemfile`

*Describe the following in the Gemfile*

{% highlight ruby %}
source 'https://rubygems.org'
gem 'rails', '5.0.0.1'
{% endhighlight %}

7. Create Gemfile.lock (empty file)

`D:\docker\test-app\Gemfile.lock`

8. Create a data folder

`D:\docker\test-app\data`

9. Create docker-compose.yml

`D:\docker\test-app\docker-compose.yml`

*Describe the following in docker-compose.yml*

{% highlight ruby %}
version: '3'
services:
  db:
    image: postgres
    volumes:
      - ./data:/var/lib/postgresql/data
    environment:
      POSTGRES_DB: "db"
      POSTGRES_HOST_AUTH_METHOD: "trust"
  web:
    build: .
    command: /bin/sh -c "rm -f /myapp/tmp/pids/server.pid && bundle exec rails s -p 3000 -b '0.0.0.0'"
    volumes:
      - .:/myapp
    ports:
      - "3000:3000"
    depends_on:
      - db
{% endhighlight %}

## App creation + settings

***

*Hinagata app creation*

`docker-compose run web rails new . --force --database=postgresql`

10. Rebuild the image

`docker-compose build`

11. Rewrite config / database.yml

{% highlight ruby %}
default: &default
  adapter: postgresql
  encoding: unicode
  host: db
  username: postgres
  password:
  pool: 5

development:
  <<: *default
  database: myapp_development

test:
  <<: *default
  database: myapp_test
{% endhighlight %}

12. Launch the app

`docker-compose up`

13. Create DB * Start and execute powershell separately from running

`docker-compose run web rake db:create`

14. Execute scaffold * Start and execute powershell separately from running

`docker-compose run web bin/rails g scaffold User name:string`

15. Apply migration * Start and execute powershell separately from running

`docker-compose run web bin/rails db:migrate`

16. Confirmation

*Access the site with a browser and check*

*http://localhost:3000*

![rails App](/assets/railsapp.png)

## Error handling
***


* If "Gem :: InstallError: XXXX requires Ruby version" appears when you execute the command in the terminal
　→ Sorry to trouble you, but let's delete the test-app created this time and start over.
　　In step 6 of file preparation, set the ruby ​​version in the Dockerfile to **2.4.0 .**

　 　`FROM ruby:2.4.0`

* If you run **http: // localhost: 3000** in your browser and get a Rails error of "key
must be 32 bytes" 　→ Sorry to trouble you, but let's delete the test-app created this time and start over....

　　In step 7 of file preparation, set the Rails version in Gemfile to **5.0.1 .**

　 　`gem 'rails', '5.0.1'`

Reference article

[Docs.docker.jp](https://docs.docker.jp/compose/rails.html)

[qiita.com](https://qiita.com/yokku21/items/a06347648d5dad5e587c)

Happy Coding :)
