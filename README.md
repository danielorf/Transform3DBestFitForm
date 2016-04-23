Windows Forms implementation of Transform3DBestFit class.

Transform3D class used to calculate best fit 3D transform between two sets of cartesian (X,Y,Z) points.
Once calculated, the following properties are available: 4x4 Transform matrix, 6DoF vector, 
Siemens NC style 6DoF vector, 4x4 Rotation matrix, 4x4 Translation matrix, fit error RMS and Rotation matrix determinant.  
This project relies on the Math.Net Numerics library.  License info contained in Transform3D.cs of Transform3DBestFit repo.


    Usage:          The Transform3D class takes in two sets of 3D points and calculates the best-fit transform and fit error RMS.
                    The point sets must first be saved as a CSV with each row representing a point pair.  The column order from 
                    left to right:  Xactual, Yactual, Zactual, Xnominal, Ynominal, Znominal.
                    The minimum number of point pairs (rows) is three with no upper limit.
                
    Terminology:    "actuals" refers to the first 2D array/matrix of points and "nominals" refers to the second 2D array/matrix 
                    of points.  The calculated transform is the best fit for actuals->nominals transform.
 
    References:     Details of SVD and rigid transform calculation can be found here:
                        http://graphics.stanford.edu/~smr/ICP/comparison/eggert_comparison_mva97.pdf
                        http://igl.ethz.ch/projects/ARAP/svd_rot.pdf
                        http://en.wikipedia.org/wiki/Wahba%27s_problem
                        http://en.wikipedia.org/wiki/Kabsch_algorithm
                        http://nghiaho.com/?page_id=671