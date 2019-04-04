#!/bin/bash

args="$@"
command="vendor/bin/phpunit $args"
echo "$command"
docker exec -it laravel-app bash -c "sudo -u devuser /bin/bash -c \"$command\""
