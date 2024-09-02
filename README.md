# Matrix Inversion Caching in R

This repository provides a pair of R functions that cache the inverse of a matrix to avoid redundant computations. The main idea is to compute the inverse of a matrix once and retrieve it from memory in subsequent calculations, saving time and computational resources.

## Functions Overview

1. **`makeCacheMatrix(matrix = matrix())`**:  
   Creates a special "matrix" object that can cache its inverse.

2. **`cacheSolve(x, ...)`**:  
   Computes the inverse of the special "matrix" returned by `makeCacheMatrix`. If the inverse has already been calculated (and the matrix has not changed), it retrieves the inverse from the cache.

## Usage

### 1. `makeCacheMatrix`

This function creates a special "matrix" object that can cache its inverse. It returns a list containing functions to:

- Set the matrix.
- Get the matrix.
- Set the inverse of the matrix.
- Get the inverse of the matrix.

#### Example

```R
# Load the functions
source("cachematrix.R")

# Create a matrix
my_matrix <- matrix(c(1, 2, 3, 4), 2, 2)

# Create a special matrix object
cached_matrix <- makeCacheMatrix(my_matrix)

# Retrieve the original matrix
cached_matrix$get()

