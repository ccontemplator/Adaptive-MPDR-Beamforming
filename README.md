# Adaptive-MPDR-Beamforming

## Host code
The Host code is defined in the following file:
```
Adaptive_Beamforming
|-/ext
    |-/xcl2
        |-xcl2.cpp
        |-xcl2.hpp
    |-utils.hpp
|-host.cpp
```

## Kernel code
The Kernel code are included in the following file:
```
Adaptive_Beamforming
|-/hw
    |-/utils
        |-x_matrix_utils.hpp #from vitis solver library
    |-qrf.hpp       #QR factorization from vitis solver library
|-dut_type.hpp      #determind the input and output type of Kernel param
|-Top_Kernel.cpp    #Top Function of the Kernel, add other kernel in this file
|-kernels.hpp       #include this file in top kernel to use the sub kernels (QRF、.etc) 

```
At present, the kernel only support the qrf function. It receive the matrix A with the row=100 and col=10. The kernel generate the matrix R and Q by applying the qrf to the matrix A and only send the matrix R (10x10) back to host side.
Therefore, the host side is designed to receive the R matrix from the kernel. To finished the whole Beamforming funcion, we have to modify both the kerenl and hostside.


## Result
We have successfully obtain the expected result, but must be patient to wait for the hardware and hardware emulation to give outputs.
However I am now trying to recover the newly updated codes and the result figure from my broken previous computer..... ;_;



