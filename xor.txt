import numpy as np

def activation(summation, threshold):
    if summation>threshold:
        return 1
    else:
        return 0


def perceptron():
    a = [0,0,1,1]
    b = [0,1,0,1]
    y = [0,1,1,0]
    threshold = 0

    w1 = [10,10]
    w2 = [10,10]

    hw = [10,-10]
    hb = [-5,-15]
    print("\nModified Input (Hidden Layer perceptro value): ")
    i = 0
    while i < 4:
        hx1 = (a[i]*w1[0]+b[i]*w1[1])+hb[0]
        hx1 = activation(hx1, threshold)
        hx2 = (a[i] * w2[0] + b[i] * w2[1]) + hb[1]
        hx2 = activation(hx2, threshold)
        summation = hx1*hw[0]+hx2*hw[1]
        o = activation(summation, threshold)
        print("\nXOR Gate for " + str(a[i]) + " " + str(b[i]) + " : " + str(o))
        i = i+1
    print("\n")
perceptron()