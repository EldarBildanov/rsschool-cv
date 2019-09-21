# Hello my lovers, here you can find my resume
 Mr. Eldar Bildanau 24 y. o.
## **Contact info**
 * e-mail: *eldar.bildanov@gmail.com*
 * Phone numbers: 
    * *+375445946779 (Belarus)*
    * *+48513122838 (Poland)*
  * What's Up: *+48513122838*
  * Viber: *+48513122838*
 ## **Summary**
 All of us are living in the rapidly changing, developing world. This world has actually plenty of possibilities, so goals and wishes for everybody are to find their own way, but for me, this way has many directions. I mean that I would like to save my name in each areas in which I can, to remain "immortal". 
 
 From childhood I used to like to discover the world. And now I've almost become a PhD in the theoretical physics. Furthermore, I like painting, cooking, playing several musicial instrument (piano, tuba, drums). 
 
 My potential will increase every year while the engine is buzzing in my a.. inside me. 
 
 ## **Skills**
 Skill | ranked
 --- | --- 
 Delphi / Pascal | :black_large_square: :black_large_square: :black_large_square: :black_large_square: :black_large_square:
 C++ / C | :black_large_square: :black_large_square: :black_large_square: :white_large_square: :white_large_square:
 Fortran | :black_large_square: :black_large_square: :black_large_square: :white_large_square: :white_large_square:
 Python | :black_large_square: :black_large_square: :black_large_square: :black_large_square: :white_large_square:
 Java | :black_large_square: :black_large_square: :white_large_square: :white_large_square: :white_large_square:
 C# | :black_large_square: :white_large_square: :white_large_square: :white_large_square: :white_large_square:
 PHP | :black_large_square: :white_large_square: :white_large_square: :white_large_square: :white_large_square:
 JS | :black_large_square: :white_large_square: :white_large_square: :white_large_square: :white_large_square:
 SQL | :black_large_square: :black_large_square: :black_large_square: :white_large_square: :white_large_square:
 HTML / CSS | :black_large_square: :black_large_square: :black_large_square: :white_large_square: :white_large_square:
 TEX / MD | :black_large_square: :black_large_square: :black_large_square: :black_large_square: :white_large_square:
 Windows / Linux | :black_large_square: :black_large_square: :black_large_square: :black_large_square: :white_large_square:

 :black_large_square: :black_large_square: :black_large_square: :black_large_square: :black_large_square: corresponds to plenty of experience and knowledge, :black_large_square: :white_large_square: :white_large_square: :white_large_square: :white_large_square: - basic knowledge and practice.
 
 There are also skills in various scientific packages such as Wolphram Mathematica, MathCad, Mapple, Matlab, OriginLab and so on as well as Python libraries: SciPy, Matplotlib.pyplot, Numpy, related to my work in the scientific field. And some graphic editors Photoshop, Inkscape, CorelDraw.
 
 ## **Code examples**
 
 For my job, I code in Pascal, C, Fortran due to huge amount of statistical data. Actually, I create a model and run some simulations, so I suppose those codes are not convinient for this CV. But anyway, I'll add the latest Python script for processing of my data files.
 
    #import requirement libraries
    import os
    import numpy as np
    import matplotlib.pyplot as plt
    from scipy.optimize import curve_fit
    
    #define function to replace ',' and '.' in file names
    def read_float_with_comma(num): 
        return float(num.replace(",", "."))
        
    #define fitting function
    def fit_func(x, a0,a1,a2,a3, t1, t2, t3):
        return a0 + a1*np.exp(-x/t1) +  a2*np.exp(-x/t2) + a3*np.exp(-x/t3)
    
    files=[]
    par_list=[]
    mu=[]
    
    #create the list of files
    for fn in os.listdir('/home/eldar/Документы/Projects/Python_projects/Fitting_curves_Evolution/all/'):
        files.append(fn);
        
    #create a list of finding optimal parameters    
    os.chdir('/home/eldar/Документы/Projects/Python_projects/Fitting_curves_Evolution/all/')
    for f in files:
        mu.append(read_float_with_comma(f[2:6]))
        data=np.genfromtxt(f)
        t = data[1:,][:-2,0]
        c = data[1:,][:-2,1]
        popt, pcov = curve_fit(fit_func, t, c, absolute_sigma = False, method = 'trf')
        sig=0
        for x in range(len(c)):
            sig+=(c[x] - fit_func(t[x],*popt))**2
        sig=(sig/(len(t)*(len(t)-1)))**1/2
        par_list.append(popt)
    time=[]
    for i in par_list:
        time.append(i[4]+i[5]+i[6])
        
    #display obtained results
    fig = plt.figure(figsize=(8.5,6), dpi=300)
    ax = fig.add_axes([0.12, 0.14, 0.88, 0.86])
    ax.scatter(mu, time)
    ax.set_ylim(0,10)
    
## **Experience**

All my programming experience is based on writing programs for simulating physicochemical systems, which I study as part of working in the European Horizon program and writing my PhD thesis. Published work results can be found [here](https://scholar.google.com/citations?user=Ve8e6CIAAAAJ&hl=ru) .
