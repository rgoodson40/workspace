# Stage 1: builder (base image that can be used for local development or for deployments)
FROM ruby:3.2.5 AS builder
RUN mkdir /workspace
WORKDIR /workspace
RUN apt-get update -qq && \
    apt-get -y install build-essential
ADD Gemfile /workspace/Gemfile
ADD Gemfile.lock /workspace/Gemfile.lock
RUN bundle install

# Stage 2: develop (for local development setup)
FROM builder AS develop

# # Stage 3: prod-build (for local development setup)
# FROM builder AS prod-build
# COPY . /workspace
# RUN rails assets:precompile
# RUN bundle config set --local without 'development test' && \
#     bundle config set --local path /rubygems
# RUN bundle install

# # Stage 4: prod (image that will be deployed in all of the environments - qa, stage, prod)
# FROM ruby:3.2.5-slim AS prod
# RUN mkdir /workspace
