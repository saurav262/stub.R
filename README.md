# stub.R
## my function description of what is done as its inverse
## for this occasion with the functions we create a special object, an array
## which stores cache in its reverse
##para esta ocasion con las funciones creamos un objeto especial , una matriz
##que almacena cache en su inversa
## stores an array and caches its inverse.

makeCacheMatrix <- function(x = matrix()){
  inv <- NULL
  set <- function(y){
    x <<- y
    inv <<- NULL
  }
  get <- function() {x}
  setInverse <- function(inverse) {inv <<- inverse}
  getInverse <- function() {inv}
  list(set = set, get = get, setInverse = setInverse, getInverse = getInverse)
}


########################
#la segunda que vamos calcular es la inversa de la matrix creada de makecachematrix 
#recuperamos la inversa en caso tal que no ha cambiado

cacheSolve <- function(x, ...){
  inv <- x$getInverse()
  if(!is.null(inv)){
    message("getting cached data")
    return(inv)
  }
  mat <- x$get()
  inv <- solve(mat, ...)
  x$setInverse(inv)
  inv
}

