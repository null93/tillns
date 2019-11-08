# tillns
> Switch faster between tiller namespaces in helm

![MIT License](https://img.shields.io/badge/License-MIT-lightgrey.svg?style=for-the-badge)
![Version 1.0.0](https://img.shields.io/badge/Version-1.0.0-lightgrey.svg?style=for-the-badge)

<!-- <p align="center" >
	<img src="docs/images/1.png" width="600" />
</p> -->

## About

`tillns` does for `helm` what `kubens` does for `kubectl`. It makes it easy to use helm by implicitly setting the tiller namespace for every helm command that is run. This is done by setting the `TILLER_NAMESPACE` environmental variable.

## Install (Homebrew)

```shell
$ brew install null93/tillns/tillns
$ echo -e "alias helm='tillns --exec'" >> ~/.bash_profile
```

## Limitations

Since a tiller deployment can be targeted with [helm](https://github.com/helm/helm) via the `--tiller-namespace` argument and the `TILLER_NAMESPACE` environmental variable only, a different approach needed to be used to solve the same problem that `kubens` solved for `kubectl`. This solution sets the `TILLER_NAMESPACE` environmental variable and passes all arguments from the `tillns --exec` command to helm. For this reason helm needs to be aliases under the formeantioned command during setup.

## Attribution

A lot of credit needs to go to the [ahmetb/kubectx](https://github.com/ahmetb/kubectx) project. This project basically applies what `kubens` does for `kubectl` but for `helm` instead.
