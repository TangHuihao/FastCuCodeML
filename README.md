# FastCuCodeML

This package is an optimization version of CuCodeML
----
Instructions for compiling using Ubuntu 18.04

you need install CUDA first

step 1:
```bash
    $your_nvcc_localation -arch=sm_75(this was mine RTX2070 sm arch you need change based on your GPU) -DCUDA -DSINGLE_GPU_ID=0 -O3 -c cuda-codeml.cu
```
step 2:
```bash
    $cc -DCUDA -DSSE -O3 -funroll-loops -fomit-frame-pointer -c tools.c
    $cc -DCUDA -DSSE -O3 -funroll-loops -fomit-frame-pointer -c codeml.c
```
step 3:
```bash
    $cc -DCUDA -DSSE -O3 -funroll-loops -fomit-frame-pointer cuda-codeml.o tools.o codeml.o -(your_cuda_lib64_location)lib64 -(your_cuda_lib_location)lib -lcudart -lstdc++ -lm -o FastCuCodeML
```

Then run the program with the following command: `your-path/FastCuCodeML`

We have tested this package in Windows10 using Visual Studio and Ubuntu 18.04 LTS
