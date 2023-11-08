# FastCuCodeML
An optimization version of CuCodeML

Instructions for compiling 

you need install CUDA first

1. $your_nvcc_localation -arch=sm_75(this was mine RTX2070 sm arch you need change based on your GPU) -DCUDA -DSINGLE_GPU_ID=0 -O3 -c cuda-codeml.cu
2. $cc -DCUDA -DSSE -O3 -funroll-loops -fomit-frame-pointer -c tools.c
3. $cc -DCUDA -DSSE -O3 -funroll-loops -fomit-frame-pointer -c codeml.c
4. 
