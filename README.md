# Ex-11---ELLIPTIC-CURVE-CRYPTOGRAPHY-ECC

## AIM:

To perform key exchange using the Elliptic Curve Cryptography (ECC) method.

## ALGORITHM:

Choose a large prime number p and an elliptic curve defined by the equation y^2 = x^3 + ax+b mod p along with a base point G on the curve. Alice and Bob choose private keys. Compute public keys: public_key = private_key G (point multiplication). Exchange public keys. Compute the shared secret: shared_secret = private_key public_key_received.

## PROGRAM:
```
#include <stdio.h>
typedef struct{
 long long int x, y;
} Point;

// Function to compute modular inverse (using Extended Euclidean Algorithm)
long long int modInverse(long long int a, long long int m) (
  long long int me m, t, q;
  long long int x 0, x1 1;
  if (m1) return 0;
  while (a > 1)
    { q=a/m;
t=m maxm, at; tx@; x0x1qx; x1 =t; } if (x10) x1 + m0; return x1;

// Function to perform point addition on elliptic curves

Point pointAddition (Point P, Point Q, long long int a, long long int p) {

Point R;

long long int lambda;

// Check if PQ (Point doubling)

if (P.x Q.x && P.y Q.y) { lambda (3 P.x P.x a) mod Inverse (2 P.y, p) %p; } else { // Point addition lambda (Q.y P.y) modInverse (Q.x P.x, p) % p;

// Calculate resulting point R.x (lambda lambda P.x R.y (lambda (P.x R.x) Q.x) %p; P.y) % p;

// Ensure values are positive R.x R.y (R.xp) % p; (R.yp) % p;

return R;

}

// Function to perform scalar multiplication (Elliptic Curve Point Multiplicat Point scalarMultiplication (Point P, long long int k, long long int a, long lon Point result = P;

k--; // Subtract 1 because we start with the base point

while (k> 0) {
```
