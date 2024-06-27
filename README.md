# Catapult Customizer Example

This is an example [repo](https://github.com/ClarifiedSecurity/catapult-customizer) to show how to Customize [Catapult](https://github.com/ClarifiedSecurity/catapult) for your organization or team needs. To use this repo you need to create your own Git project (in a Git server of your choice) and then fill it out with the examples shown here. After that is done fill out `MAKEVAR_CATAPULT_CUSTOMIZER_REPO` in your Catapult's `.makerc-vars` file to include the customizations.

**DELETE ALL CUSTOMIZATION FOLDER AND FILE EXAMPLES THAT YOU WILL NOT BE USING** - Otherwise empty folder will be included overriding the default files.

The structure of the customization repo is as follows:

## Folders

- `certificates` - Contains the trusted certificate files that will be installed into the container. The certificate format must be base64 and the file name format must be <certificate_name>.crt

- `container` - Contains .custom_aliases file that will be copied into the container. Refer to the [.default_aliases](https://github.com/ClarifiedSecurity/Catapult/blob/main/container/home/builder/.default_aliases) file as an example on how to create .custom_aliases.

- `docker` - Contains custom docker-compose-extra.yml to add extra environment variables to the container. Refer to the default [docker-compose-extra.yml](https://github.com/ClarifiedSecurity/Catapult/blob/main/defaults/docker-compose-extra.yml) for an example. Also contains docker-compose-personal.yml that will be created on first run. This file is used to store personal environment variables that you don't want to commit to the repo.

- `docker-entrypoints` - Contains custom docker-entrypoint scripts that will run inside the container during `make start`. Refer to default [entrypoint](https://github.com/ClarifiedSecurity/Catapult/tree/main/scripts/entrypoints) scripts for examples.

- `makefiles` - Contains custom .makerc\* files specific to your organization or project. Refer to the default [.makerc](https://github.com/ClarifiedSecurity/Catapult/blob/main/.makerc) file for examples and the [Makefile](https://github.com/ClarifiedSecurity/Catapult/blob/main/Makefile#L3-L5) for different types of makefiles that get loaded if they exists.

- `scripts` - Contains custom scripts that can be used with the project. For example with `make` commands

- `start-tasks` - Contains scripts that will be run on the host during container startup. Refer to existing [start-tasks](https://github.com/ClarifiedSecurity/Catapult/tree/main/scripts/start-tasks) for examples.

## Files

- `start.yml` - In some rare cases you might want to customize the deployment tree of Catapult. For that you can create your own start.yml file and it will be used instead of the default one. Refer to the default [start.yml](https://github.com/ClarifiedSecurity/Catapult/blob/main/defaults/start.yml) as an example.

- `autocomplete.yml` - Contains custom completion commands that can be used with the `ctp` command in the container. Refer to the default [autocomplete.yml](https://github.com/ClarifiedSecurity/catapult/blob/main/defaults/autocomplete.yml) as an example.
