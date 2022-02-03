## Βήμα 1ο

 ### Ερώτημα 1
 
|   |bzip   | hmmer   | libm   | mcf  | sjeng |
|---|---|---|---|---|---|
|commited inst.  | 100000001  |16502   | 12883  |1000000001 |100000001|
| l1d block replacements  | 710569  |12   | 4  |54452   |5262377
|l2 accesses   | 712341| 800| 542 | 724390 | 526405|



![sim secs](https://github.com/username644/erg.Aoc2/blob/main/sim%20secs.png?raw=true)
![sim secs 1,5](https://github.com/username644/erg.Aoc2/blob/main/sim%20seconds%201,5.png?raw=true)

![CPI.png](https://github.com/username644/erg.Aoc2/blob/main/CPI.png?raw=true)
![CPI1,5.png](https://github.com/username644/erg.Aoc2/blob/main/CPI%201,5.png?raw=true)

![l1 d miss](https://github.com/username644/erg.Aoc2/blob/main/l1d%20missrate.png?raw=true)
![l1 d miss 1,5](https://github.com/username644/erg.Aoc2/blob/main/L1d%20missrate%201,5.png?raw=true)

![l1i missrate](https://github.com/username644/erg.Aoc2/blob/main/l1i%20missrate.png?raw=true)
![l1i missrate1,5](https://github.com/username644/erg.Aoc2/blob/main/L1i%20missrate%201,5.png?raw=true)

![l2 missrate](https://github.com/username644/erg.Aoc2/blob/main/l2%20missrate.png?raw=true)
![l2 missrate 1,5.png](https://github.com/username644/erg.Aoc2/blob/main/l2%20missrate%201,5.png?raw=true))

#### c. 
Με τη χρήση π.χ. του number of misses  και του miss rate  στην l2 cache μπορεί να υπολογιστεί ο αριθμός των access στην l2 cache .


### Eρώτημα 3
Όπως φαίνεται και από τα options του gem5 ( sys-clock, cpu-clock) μόνο τα block που τρέχουν στη CPU αλλάζουν συχνότητα. Εάν γινόταν προσθήκη δεύτερου επεξεργαστή θα δούλευε λογικά στη συχνότητα του συστήματος.



## Βήμα 2ο 
![zip](https://github.com/username644/erg.Aoc2/blob/main/zip%20eper.png?raw=true)
 
![hmmer](https://github.com/username644/erg.Aoc2/blob/main/hmmer%20exper.png?raw=true)
![lbm](https://github.com/username644/erg.Aoc2/blob/main/lbm%20exper.png?raw=true)
![mcf](https://github.com/username644/erg.Aoc2/blob/main/mcf%20exper.png?raw=true)




## Βήμα 3ο 


Για το κόστος της κάθε επιλογής λαμβάνουμε υπόψη το άθροισμα του χρηματικού κόστους κάθε επιλογής και της πολυπλοκότητάς της. Έχοντας κατά νου να δώσουμε μια κατά το δυνατόν ρεαλιστική εικόνα του κόστους κάθε επιλογής, συλλέξαμε δεδομένα από κατά το δυνατόν ρεαλιστικές πηγές και καταλήξαμε στην εξής συνάρτηση κόστους:

  Κ = [Α(L1i_size/32kB * L1i_assoc) + B(L1d_size/32kB * L1d_assoc) + C(L2_size/1MB * L2_assoc)] * cache_line_size/32

-    c κόστος λόγω associativity
-   a_L1i associativity της L1 instruction cache
-   a_L1d associativity της L1 data cache
-   a_L2 associativity της L2 cache
-   s_L1i μέγεθος της L1 instruction cache σε KB
-   s_L1d μέγεθος της L1 data cache σε KB
-   s_L2 μέγεθος της L2 cache σε KB


Γνωρίζουμε πως η L1είναι πιό ακριβή ανά byte από την  L2 , άρα θέτουμε A=5c. Η L1 instruction cache είναι πιο ακριβής, και επομένως πιο φθηνή, σε σχέση με τη data cache. Άρα θέτουμε Β = 2 * Α.

Για να δούμε ποιά αρχιτεκτονική θα εφαρμόσουμε, πρέπει να επιλέξουμε τις τιμές που ελαχιστοποιούν την συνάρτηση κόστους-χρόνου εκτέλεσης, η οποία είναι η εξής:
func = K * CPI

Πιο κάτω φαίνονται τα διαγράμματα για κάθε benchmark:


 


 
 


 

Ακριβής τιμές:

cost zip
|---|---|
|1|	55|
|2|	119|
|3|	607|
|4	|1212|
|5|	1600|

hmmer
|build|cost|
|---|---|
|1|	16|
|2|	31|
|3|	63|
|4|	50|
|5|	68|
|6|	455|



cost libm
|---|---|
|1|	173|
|2|	120|
|3|	2506|
|4|	204|

cost mcf
|---|---|
|1	|34|
|2	|70|
|3|	17|
|4|	97|
|5|	884|
|6	|378|




### Κριτική 

Δυστυχώς δεν υπήρχε αρκετός χρόνος για την πλήρωση των ερωτημάτων
