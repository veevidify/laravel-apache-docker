#!/bin/bash

args="$@"
command="composer $args"
echo "$command"
docker exec -it laravel-app bash -c "sudo -u devuser /bin/bash -c \"$command\""
