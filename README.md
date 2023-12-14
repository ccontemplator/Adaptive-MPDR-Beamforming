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
The kernel was designed to support only the qrf function. It receive the matrix A with the row=100 and col=10. The kernel generates the matrix R and Q by applying the qrf to the matrix A.
And the host side is designed to send the input data matrix into the kernel.


## Result
We have successfully obtain the expected result, but one must be patient to wait for the hardware and hardware emulation to give outputs.
Please check out the report to understand what we were doing.

NOTE: under maintenance, still recovering codes from the broken SSD.



