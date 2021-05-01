# tscheme

Toy-scheme

## Feature

- [ ] 四则运算
- [ ] 函数调用
- [ ] IO
- [ ] 条件判断
- [ ] 类型推导  

## Demo

```
; 四则运算
42
(+ 2 3)

; 函数
(def (add a b)
    (+ a b))
(add 3 4)

; 递归函数
(def (fac n) 
    (if (eq? n 0) 
        1
        (* n (fac (- n 1)))
    )
)
(print "fac(10) is " (fac 10))

; IO
(print "Hello world")
(print 42)
(print (+ 2 3))
(print (add read read))
```

## Token 类型

```
Paren = (|)
Number = (0-9)*.?(0-9)*
Name = .*
Op +|-|*|/
```

## 文法

```
Expr ::= Number                 ; NumberExpr
    | Name                      ; VarExpr
    | (Name Expr...)            ; CallExpr 
FunctionExpr ::= (def (Name Name...) Expr) ; FunctionExpr
