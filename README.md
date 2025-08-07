# Numerical-Analysis-of-Differential-Equations
This repository contains several numerical methods for solving ODE's, and the method of lines for PDE's, and some analytical theory surrounding numerical analysis.

Motivation: Differential equations are a key concept in several scientific fields, such as physics, engineering, economics, biology, applied mathematics, weather prediction, and many more. It is often the case that solving a differential equation analytically is not practical for the people working, and some differential equations may not even be possible to solve. For this reason it is crucial that we have numerical analysis to see what the solution is without actually needing to have it algebraically expressed. These numerical methods can take any system of first degree ODEs and graph the solution (given certain parameters are met), additionally ODEs of order 2 or higher can be converted to a system of first order ODEs and solved using these methods. Numerically solving differential equations can provide very useful insight into the nature of a problem for people working in just about any scientific field, and additionally can help mathematicians get an idea for what a true solution should look like when they are researching differential equations.

Contents: In the matlab files provided there are several numerical methods for ODEs, including implicit or explicit methods, explicit Runge-Kutta methods, and multi-step methods which are both implicit and explicit. Additionally I have used matlab to plot the absolute stability of the methods provided and made a matlab file that will bound the global error of the Foreward Euler method. Additionally I used a 4th order Runge-Kutta method which I made, to solve an example PDE (the heat equation in one spatial dimension) by the method of lines, converting it into a system of ODEs. The LaTeX files attatched in this README will provide derrivations and proofs of much of the contents in this project, including derrivations of the multistep methods, analysis of the absolute stability, proof of the theorem I used to bound the error of the Forward Euler method, and derrivations of the local truncation error of some methods. 

The Numerical Methods folder includes the matlab code used to numerically solve these ODEs and in that folder is the PDEs folder which includes my method of lines example. The stability plots folder includes matlab code which will prot the absolute stability of the methods when ran. The Forward_Euler_Error.md file will give the global error for the Forward Euler method given a specific ODE, assuming some basic conditions are met. 

How to use: In order to use the numerical methods, you need to input a function (or system) f(t,y(t)) which equals y'(t) (for systems you can have y be a vector) and run the code, it will output a plot of the estimated true solution (feel free to change the settings on the plot such as the bounds in order to suit your specific problem). You may need to change N which reprisents the total number of timesteps taken by the program, especially for explicit non-multistep methods, because (as you will see in the stability plot) some of them need a relatively small value of h (the size of each timestep) to converge to the true solution. There are several parameters you will need to input for the Forward Euler bound and will require a bit of math from the user (the smallest possible Lipschitz contant on your time interval is needed, and the infinity norm of the second derrivative of y is needed) but after that you just run the code and the global error bound is outputted. For the stability plots just press run!

Visuals: here are some examples of outputs of the code I made.

1: An approximate solution of the equation y'(t)=-10y(t) with initial condition y(0)=1 using my Backwards Euler method.
![Image](https://github.com/user-attachments/assets/61efddc3-65e1-4bca-9ddb-18ce40f76e35)

2: My approximated solution for the heat equation in one spatial dimension (using the method of lines)
![Image](https://github.com/user-attachments/assets/f7d3a4c6-dc12-4e42-a019-4d8294c52973)

3: My stability plot of my 4th order Runge-Kutta method, with the stable area shaded green (see my PDFs for the derrivation of this)
![Image](https://github.com/user-attachments/assets/8d2db7bc-c492-49c3-8d66-c8caa85ebca1)

4: My 4th order Runge-Kutta approximation for y'(t)=cos(t^2), with initial condition y(0)=0
![Image](https://github.com/user-attachments/assets/654c1189-296c-448d-80a9-a72d3cd73a34)

5: My 3rd order Backward Differentiation approximation for y'(t)=-50y(t) with initial condition y(0)=1
![Image](https://github.com/user-attachments/assets/b1b09f74-a884-49c4-8c1c-b640c7c4fc92)

My LaTeX work: here is some proofs and derrivations I did to support and analyze my programs.

Here's a brief explainantion of a theorem used to bound the error for the forward Euler method, along with a proof of said theorem.
[Forward_Euler_Error_Bound.pdf](https://github.com/user-attachments/files/21604741/Forward_Euler_Error_Bound.pdf)

Derrivations for an Adams-Bashforth method:
[3rd_order_Adams-Bashforth](https://github.com/user-attachments/files/21670078/AB3_derrivation.pdf)
