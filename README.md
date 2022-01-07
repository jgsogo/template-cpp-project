
> ## After installing this template
> This is just a template to start working in a C++ project. It includes basic folder
> structure using CMake and Catch2 test framework. It also included some basic Conan files
> to grab dependencies and start working with CIs.
> 
> Search for TODO comments to apply the changes that are required to your specific project
> and spend some time having a look to '.github/workflows' files to adjust them to your needs
> 
> Most of this template is thought to work together with 'https://github.com/jgsogo/conan-recipes'
> repository, you might need to move some of those files to your own organization.


## Build and run locally

```
mkdir cmake-build-xxxx && cd cmake-build-xxxx
```

```
conan lock create --profile:host=../.conan/profiles/cpp20 --profile:build=default --lockfile=../lockfile.json --lockfile-out=lockfile.json --name=cpp-project --version=0.1 ../conanfile.txt --build --update
```

```
conan install --lockfile=lockfile.json ../conanfile.txt --build=missing --generator=virtualenv
```

## Update dependencies

```
conan lock create --name=composite --version=0.1 --base --lockfile-out lockfile.json conanfile.txt --build --profile:host=.conan/profiles/cpp20 --profile:build=default
```
