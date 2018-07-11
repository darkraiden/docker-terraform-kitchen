# Terraform and Ruby for kitchen tests

This repository automatically builds containers for using the `terraform` command line program and `ruby` for `test-kitchen`.

## Getting Started

These instructions will cover usage information and for the docker container

### Prerequisities


In order to run this container you'll need docker installed.

* [Windows](https://docs.docker.com/windows/started)
* [OS X](https://docs.docker.com/mac/started/)
* [Linux](https://docs.docker.com/linux/started/)

### Usage

#### Container interaction

You can use this version with the following command:

```shell
docker run -it davidedimauro88/terraform-kitchen:latest /bin/bash
```

For example: start the container sharing your current working directory:

```shell
docker run -v $(pwd):/terraform-module -w /terraform-module -it davidedimauro88/terraform-kitchen:latest /bin/bash
```

#### Environment Variables

* `TERRAFORM_VERSION` - The version of Terraform to be installed
* `BUILD_PACKAGES` - The packages used to build the image
* `GEM_PACKAGES` - The Ruby gems used to run test kitchen and awspec

## Built With

* `ruby`

## Find Us

* [GitHub](https://github.com/darkraiden/docker-terraform-kitchen)

## Contributing

We Use [Github Flow](https://guides.github.com/introduction/flow/index.html), So All Code Changes Happen Through Pull Requests
Pull requests are the best way to propose changes to the codebase (we use [Github Flow](https://guides.github.com/introduction/flow/index.html)). We actively welcome your pull requests:

1. Fork the repo and create your branch from `master`.
2. If you've added code that should be tested, add tests.
3. If you've changed APIs, update the documentation.
4. Ensure the test suite passes.
5. Make sure your code lints.
6. Issue that pull request!

## Authors

* [Davide Di Mauro](https://github.com/darkraiden)

See also the list of [contributors](https://github.com/darkraiden/docker-terraform-kitchen/contributors) who
participated in this project.

## License

This project is licensed under the MIT License.
