# CS677-Project-23-24-I

## Problem Statement:

Performing volume rendering of large datasets poses a challenge due to computational constraints. Traditional sequential methods fall short resulting in impractical rendering times. The key challenge is to enhance the speed of the ray casting algorithm, a critical component in volume rendering, through parallelization across multiple processes.

## Technical Method:

First, we utilize the Mpi4Py library in order to distribute the 3D dataset equally among 'n' processes (as specified by the user) along the Z-axis. Now, we built a transfer function that applies the ray-casting algorithm on each of these processes parallely. The transfer function then maps scalar values to RGBA color and opacity values based on a combination of exponential functions. </br>
With parts of our 2D image ready in different processes, we gather these processed data slices back to the root using MPI communication. 

## Results:

We compared our GUI results to Paraview Visualization Software, a benchmark for open-source scientific data visualization.

![image](https://github.com/user-attachments/assets/86bca5db-7647-430a-b39f-692dfea6e5af)

We also evaluated the performance of our model (time taken to render the dataset) with respect to the number of processes for two datasets of varying sizes.

![image](https://github.com/user-attachments/assets/1f053617-2c2c-48a0-9519-29d1150095c9)

We observe an initial performance improvement up to 5 processes for the smaller-sized dataset, followed by a decline, ultimately stabilizing. Conversely, the larger-sized dataset exhibits optimal performance with 4 processes.

## Conclusion:

In conclusion, this project successfully addressed the challenge of rendering large volumetric datasets through the use of MPI for parallel computing. We achieved efficient volume rendering, enabling faster and scalable visualization of volumetric data.

We also suggested some avenues for future work on this project that focus on improved performance and user interaction with the GUI.
