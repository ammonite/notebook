notebook
========
English land law
英国的土地法律
http://stackoverflow.com/questions/18767523/fitting-data-with-numpy
>>> x
array([ 3.08,  3.1 ,  3.12,  3.14,  3.16,  3.18,  3.2 ,  3.22,  3.24,
    3.26,  3.28,  3.3 ,  3.32,  3.34,  3.36,  3.38,  3.4 ,  3.42,
    3.44,  3.46,  3.48,  3.5 ,  3.52,  3.54,  3.56,  3.58,  3.6 ,
    3.62,  3.64,  3.66,  3.68])

>>> y
array([ 0.000857,  0.001182,  0.001619,  0.002113,  0.002702,  0.003351,
    0.004062,  0.004754,  0.00546 ,  0.006183,  0.006816,  0.007362,
    0.007844,  0.008207,  0.008474,  0.008541,  0.008539,  0.008445,
    0.008251,  0.007974,  0.007608,  0.007193,  0.006752,  0.006269,
    0.005799,  0.005302,  0.004822,  0.004339,  0.00391 ,  0.003481,
    0.003095])
Now, I want to fit these data with, say, a 4 degree polynomial. So I do:

>>> coefs = np.polyfit(x, y, 4)
>>> ffit = np.poly1d(coefs)
Now I create a new grid for x values to evaluate the fitting function ffit:

>>> x_new = np.linspace(x[0], x[-1], num=len(x)*10)
When I do all the plotting (data set and fitting curve) with the command:

>>> fig1 = plt.figure()                                                                                           
>>> ax1 = fig1.add_subplot(111)                                                                                   
>>> ax1.scatter(x, y, facecolors='None')                                                                     
>>> ax1.plot(x_new, ffit(x_new))                                                                     
>>> plt.show()
