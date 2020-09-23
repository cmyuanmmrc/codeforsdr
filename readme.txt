The step to test the algorithm is as follows:

Open the Mathematica algorithm
.
Step 1. Quit the kernel.
Step 2. Input the difference polynomial system in the given form, where  uij[k] are parameter variables and y [r, s] are dependent variables.
Step 3. With the package, it will return the strong essential system of algebraic case, whose sparse resultant can be computed by submixed method appearing in the link 
http : // cgi.di.uoa.gr/~emiris/soft_alg.html.




As an expamle, for a difference system input like this:



P0 = u00[i] + u01[i] y[1, i + 1]^2 y[2, i + 1]^2 y[3, i + 1] + 
   u02[i] y[1, i]^2 y[2, i] y[3, i] y[4, i] y[4, i + 1];

P1 = u10[i] + u11[i] y[1, i + 1]^2 y[2, i + 1]^2 y[3, i + 1] + 
   u12[i] y[1, i + 1]^2 y[2, i + 1] y[3, i + 1] y[4, i + 1] y[4, 
     i + 2];

P2 = u20[i] + u21[i] y[1, i + 2]^2 y[2, i + 2]^2 y[3, i + 2] + 
   u22[i] y[1, i + 1]^2 y[2, i + 1]^2 y[3, i + 1] + 
   u23[i] y[1, i]^2 y[2, i] y[3, i] y[4, i] y[4, i + 1];

P3 = u30[i] + u31[i] y[1, i + 1] y[2, i + 1] + 
   u32[i] y[1, i + 1]^2 y[2, i + 1] y[3, i + 1] y[4, i + 2];
P4 = u40[i] + u41[i] y[1, i + 1] y[3, i + 2] y[4, i + 1] + 
   u42[i] y[1, i + 1]^2 y[2, i + 2] y[4, i];

polset = {P0, P1, P2, P3, P4};



Run the whole Mathematica program for "polset", results the following: 



Super-essential system is
{-y[1,i]-y[1,1+i]+y[1,2+i],u[i]+y[1,1+i]^2-y[1,i] y[1,2+i]-y[2,i],y[2,i]+y[2,1+i]}.
Strong essential system is
{-z[1]-z[2]+z[3],-z[2]-z[3]+z[4],-z[3]-z[4]+z[5],-z[4]-z[5]+z[6],u[i]+z[2]^2-z[1] z[3]-z[7],u[1+i]+z[3]^2-z[2] z[4]-z[8],-1+u[3+i]+z[5]^2-z[4] z[6],z[7]+z[8],z[8]+z[9],1+z[9]}.


Then run the Maple package(The algebraic sparse resultant method package provided by Emiris) to get the final difference resultant.


Matrix(7, 7, {(1, 1) = u10[1+i], (1, 2) = u11[1+i], (1, 3) = u12[1+i], (1, 4) = 0, (1, 5) = 0, (1, 6) = 0, (1, 7) = 0, (2, 1) = u20[i], (2, 2) = u21[i], (2, 3) = 0, (2, 4) = u22[i], (2, 5) = 0, (2, 6) = 0, (2, 7) = u23[i], (3, 1) = u00[2+i], (3, 2) = 0, (3, 3) = u02[2+i], (3, 4) = 0, (3, 5) = 0, (3, 6) = u01[2+i], (3, 7) = 0, (4, 1) = u10[i], (4, 2) = 0, (4, 3) = 0, (4, 4) = u11[i], (4, 5) = u12[i], (4, 6) = 0, (4, 7) = 0, (5, 1) = u00[1+i], (5, 2) = u01[1+i], (5, 3) = 0, (5, 4) = 0, (5, 5) = u02[1+i], (5, 6) = 0, (5, 7) = 0, (6, 1) = u20[1+i], (6, 2) = u22[1+i], (6, 3) = 0, (6, 4) = 0, (6, 5) = u23[1+i], (6, 6) = u21[1+i], (6, 7) = 0, (7, 1) = u00[i], (7, 2) = 0, (7, 3) = 0, (7, 4) = u01[i], (7, 5) = 0, (7, 6) = 0, (7, 7) = u02[i]}).