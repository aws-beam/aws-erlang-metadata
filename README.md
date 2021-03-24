# Superseded; please use aws_credentials instead

This project has been archived and superseded by [aws_credentials](https://github.com/aws-beam/aws_credentials) 

We very strongly encourage you to use that project for any new development.

# AWS instance metadata support for aws-erlang

[![Build Status](https://travis-ci.org/jkakar/aws-erlang-metadata.svg)](https://travis-ci.org/jkakar/aws-erlang-metadata)

Fetch up-to-date credentials from the EC2 instance metadata service to use
with [aws-erlang](https://github.com/jkakar/aws-erlang).  Credentials are
automatically refreshed in the background.

Here is an example:

```erlang
{ok, _} = application:ensure_all_started(aws_metadata),
Client = aws_metadata:get_client(),
{ok, Output, _Response} = aws_kinesis:list_streams(Client, #{}, []),
io:format("~p~n", [Output]).
```
