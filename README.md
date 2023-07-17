# Catapult Customizer Example repo

This is an example repo to show how to Customize [Catapult](https://github.com/ClarifiedSecurity/catapult) for your organization's or project's needs.
To use this repo you need to create your own Git project (in a Git server of your choice) and then fill it out with the examples shown here. After that is done fill out `MAKEVAR_CATAPULT_CUSTOMIZER_REPO` in your .makerc-vars to include the customization repo.

**DELETE ALL CUSTOMIZATION FOLDER AND FILE EXAMPLES THAT YOU WILL NOT BE USING**

The structure of the customization repo is as follows:

## Folders

- `certificates` - Contains the trusted certificate files that will be installed into the catapult container. The certificate format must be base64 and the file name format must be <certificate_name>.crt

- `container` - Contains .custom_aliases file that will be copied into the container refer to the [.default_aliases](https://github.com/ClarifiedSecurity/Catapult/blob/main/container/home/builder/.default_aliases) file as an example on how to create .custom_aliases.

- `docker` - Contains custom docker-compose-extra.yml to add extra environment variables to the Catapult container. Refer to the default [docker-compose-extra.yml](https://github.com/ClarifiedSecurity/Catapult/blob/main/defaults/docker-compose-extra.yml) for an example

- `docker-entrypoints` - Contains custom docker-entrypoint scripts that will ran on container startup. Refer to default [entrypoint](https://github.com/ClarifiedSecurity/Catapult/tree/main/scripts/entrypoints) scripts for examples.

- `makefiles` - Contains custom .makerc\* files specific to our organization or project. Refer to the default [.makerc](https://github.com/ClarifiedSecurity/Catapult/blob/main/.makerc) file for examples. and the [Makefile](https://github.com/ClarifiedSecurity/Catapult/blob/main/Makefile#L3-L5) for different types of makefile variable extensions that get loaded if they exists.

- `poetry` - Contains custom pyroject.toml and poetry.lock files that will be used to install the Python dependencies. Refer to the defaults [pyproject.toml](https://github.com/ClarifiedSecurity/Catapult/tree/main/defaults) for examples.

- `requirements` - Contains different \*.yml files that will be used to install the Ansible roles and collections refer to [Ansible docs](https://docs.ansible.com/ansible/latest/collections_guide/collections_installing.html) or default [requirements](https://github.com/ClarifiedSecurity/Catapult/tree/main/defaults)

- `scripts` - Contains custom scripts that will be used with the project

- `start-tasks` - Contains scripts that will be ran on the host during container startup. Refer to existing [start-tasks](https://github.com/ClarifiedSecurity/Catapult/tree/main/scripts/start-tasks) for examples.

## Files

- `example.makerc-vars` - When using non-default example.makerc-vars then make sure that it's is also defined in the Catapult Customizer repo because there are helper scripts that will check if your .makerc-vars contains all of the variables from example.makerc-vars.

- `start.yml` - In some rare cases you might want to customize the deployment tree of Catapult. For that you can create your own start.yml file and it will be used instead of the default one. Refer to the default [start.yml](https://github.com/ClarifiedSecurity/Catapult/blob/main/defaults/start.yml) as an example.
