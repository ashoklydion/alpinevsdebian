# alpinevsdebian
This is alpine vs debian test banchmark

```bash
BN="import timeit; print(timeit.timeit('import json; json.dumps(list(range(10000)))', number=5000))"

$docker run python:3.7-alpine python -c "$BN"
6.729875800010632


$docker run python:3.7 python -c "$BN"
4.4239668999944115


BN2="import timeit; print(timeit.timeit('for x in range(0, 1000): pass', number=5000))"

$docker run python:3.7 python -c "$BN2"
0.07339710000087507 
$docker run python:3.7-alpine python -c "$BN2"
0.07989409999572672

BN3="import timeit; print(timeit.timeit('for x in range(0, 10000): pass', number=5000))"

$docker run python:3.7 python -c "$BN3"
0.8640040000027511
 $docker run python:3.7-alpine python -c "$BN3"
0.8806269000051543

BN3="import timeit; print(timeit.timeit('for x in range(0, 100000): pass', number=5000))"

$docker run python:3.7 python -c "$BN3"
8.769016800011741
 $docker run python:3.7-alpine python -c "$BN3"
8.962896799988812

```
