#!/bin/bash

args="$@"
command="php artisan $args"
echo "$command"
docker exec -it laravel-app bash -c "sudo -u devuser /bin/bash -c \"$command\""
