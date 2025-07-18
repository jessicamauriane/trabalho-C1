import numpy as np

def f(x):
    return np.sin(x)

def derivada_diferencas_finitas(f, x, h=1e-5):
    return (f(x + h) - f(x - h)) / (2 * h)

def soma_riemann(f, a, b, n):
    dx = (b - a) / n
    x = np.linspace(a, b - dx, n)
    return np.sum(f(x) * dx)

a = 0
b = np.pi
n = 1000
x0 = np.pi / 4

derivada = derivada_diferencas_finitas(f, x0)
print(derivada)

integral = soma_riemann(f, a, b, n)
print(integral)
