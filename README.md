# 1
R programming coursera assginment 3 
## Put comments here that give an overall description of what your
## functions do

## Write a short comment describing this function

makeCacheMatrix <- function(x = matrix()) {
inv<-NULL
set<-function(y){
	x<<-y
	inv<<-NULL
}
get<-function()x
setinverse<-function(inverse)inv<<-inverse
getinverse<-function()inv
list(set=set,get=get,setinverse=setinverse,getinverse=getinverse)
}
##This function creates a special matrix object that can cache its inverse##

## Write a short comment describing this function

cacheSolve <- function(x, ...) {
        ## Return a matrix that is the inverse of 'x'
        inv<-x$getinverse()
        if(!is.null(inv)){
        	message("getting cached data")
        	return(inv)
        }
        data<-x$get()
        inv<-solve(data,...)
        x$setinverse(inv)
        inv
}

##This function computes the inverse of the special matrix that the makeCacheMatrix command gives. If the inverse has already been calculated and the matrix remains the same, then this new function will retrieve the inverse from the cache. 
