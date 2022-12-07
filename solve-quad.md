Here is a possible R code that defines a function called solve_quad that takes three arguments: a, b, and c, representing the coefficients of a quadratic equation in the form ax^2 + bx + c = 0. The function calculates the solutions of the quadratic equation and returns them as a list:

Copy code
solve_quad <- function(a, b, c) {
  if (a == 0) {
    # Handle the case of a linear equation
    x <- -c / b
    return(list(x))
  }
  else {
    # Compute the discriminant
    d <- b^2 - 4*a*c
    if (d < 0) {
      # Handle the case of complex roots
      x1 <- -b / (2*a)
      x2 <- sqrt(-d) / (2*a)
      return(list(complex(real=x1, imaginary=x2), complex(real=x1, imaginary=-x2)))
    }
    else if (d == 0) {
      # Handle the case of a single real root
      x <- -b / (2*a)
      return(list(x))
    }
    else {
      # Handle the case of two real roots
      x1 <- (-b + sqrt(d)) / (2*a)
      x2 <- (-b - sqrt(d)) / (2*a)
      return(list(x1, x2))
    }
  }
}
To use this function, you can call it with the appropriate values for a, b, and c. For example, to solve the quadratic equation 2x^2 + 5x - 3 = 0, you can call the function as follows:

Copy code
solve_quad(2, 5, -3)
This will return the solutions of the equation, which are -3 and 0.5. Note that the solutions are returned as a list, so if you want to access a specific solution, you can use the [[]] notation to extract it from the list. For example:

Copy code
solutions <- solve_quad(2, 5, -3)
x1 <- solutions[[1]]
x2 <- solutions[[2]]
This will assign the first solution to x1 and the second solution to x2.
