# How to convert a Dockerfile to a singularity recipe


Get the singularitypython package
```
pip install spython
```

then

```
spython recipe Dockerfile >> Singularity.snowflake
```

# Build singularity image

On a machine where you can build singularity (for me this is another container)

```
sudo singularity build container_name SFile
``` 

This should work in principle, but I got errors about unupported Bootstrap types
that I didn't manage to find a quick fix for.

Instead, I simply uploaded my finished Docker image to Dockerhub
and then built the singularityimage from there:

```
singularity build elastix.simg docker://opticalflow/elastix:firsttry
```