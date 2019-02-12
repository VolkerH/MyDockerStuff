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

sudo singularity build container_name SFile
