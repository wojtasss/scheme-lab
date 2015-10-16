###Zadanie 2
Proszę napisać funkcje nwd a b oraz nww a b, których wartościami są największy wspólny dzielnik i najmniejsza wspólna wielokrotność. 
```scheme
(define (nwd a b)(if (not (= a b)) (if (> a b) (nwd (- a b) b) (if (< a b) (nwd a (- b a)))) a))
```
###Zadanie 3
Proszę napisać funkcję (new.< x y), (new.> x y), (new.= x y), (new.<= x y), (new.>= x y) oraz (new.<> x y). Należy z wbudowanych funkcji używać wyłącznie funckcję < (oraz predykaty oczywiście). 
```scheme
(define (new.< x y)(if (< x y) x y))                              #| funkcja new.<  |#
(define (new.> x y)(if (< x y) y x))                              #| funkcja new.<  |#
(define (new.= x y)(if (< x y) #f (if (< y x) #f #t)))            #| funkcja new.=  |#
(define (new.<= x y)(if (new.= x y) #t (if (< x y) #t #f)))       #| funkcja new.<= |#
(define (new.>= x y)(if (new.= x y) #t (if (< x y) #f #t)))       #| funkcja new.>= |#
(define (new.<> x y)(if (new.= x y) #f #t))                       #| funkcja new.<> |#
```
###Zadanie 4
Proszę napisać funkcję (same-values? p1 p2 x y), której wartość jest #t, jeżeli (p1 x y) i (p2 x y) mają tą samą wartość i #f w przecziwnym przypadku.
```scheme
(define (same-values? p1 p2 x y)(if (or (and (not (p1 x y)) (not (p2 x y))) (and (p1 x y) (p2 x y))) #t #f))
```
###Zadanie 5
Proszę napisać funkcje (odd? n) oraz (even? n), które sprawdzają, czy liczba naturalna n jest nieparzysta względnie parzysta. Należy używać wyłącznie funkcje #t, #f, zero? oraz "-1".
```scheme
(define (new.odd? n) (if (zero? n) #f (if (new.odd? (- n 1)) #f #t)))       #| funkcja new.odd  |#
(define (new.even? n) (if (zero? n) #t (if (new.even? (- n 1)) #f #t)))     #| funkcja new.even |#
```
###Zadanie 6
Proszę napisać rekurencyjną oraz iteracyną funkcję (fib n), która obliczy n-tą liczbę Fibonacci. 
```scheme
(define (fib x)(cond ((= x 0) 0) ((= x 1) 1) (else (+ (fib (- x 1)) (fib (- x 2))))))
```
###Zadanie 7
Proszę napisać rekurencyjną oraz iteracyjną funkcję (exp b e) na podstawie tej właściwości. Używając model środowiska, proszę pokazywać, jak wyrażenie (exp 2 6) zostaje ewaluowane. 
* Rekurencyjnie
```scheme
(define (exp b e)(if (= e 1) b (square (exp b (/ e 2)))))
```
* Iteracyjnie
```scheme
```
