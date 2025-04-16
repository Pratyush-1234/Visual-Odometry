# Visual-Odometry
This project implements a monocular visual odometry pipeline from scratch using classical computer vision techniques. The pipeline processes a sequence of 801 frames and estimates the camera trajectory.
The following is an overview of the entire algorithm:
1. Find the corresponding features between frames Ik and Ik−1.
2. Using these feature correspondences, estimate the essential matrix between the two images within a RANSAC
scheme.
3. Decompose the essential matrix to obtain the relative rotation Rk and translation tk, and form the transformation
Tk.
4. Scale the translation tk with the absolute or the relative scale.
5. Concatenate the relative transformation by computing Ck = Ck−1Tk, where Ck−1 is the previous pose of the
camera in the world frame.
6. Repeat the above steps for the remaining pairs of frames.
