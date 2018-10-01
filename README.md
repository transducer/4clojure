_Markdown 4clojure solutions generated with_ [_4clojure-to-md_](github.com/transducer/4clojure-to-md)


[#1 Nothing but the Truth [Elementary]](http://www.4clojure.com/problem/1)

```
true
```


[#2 Simple Math [Elementary]](http://www.4clojure.com/problem/2)

```
4
```


[#3 Intro to Strings [Elementary]](http://www.4clojure.com/problem/3)

```
"HELLO WORLD"
```


[#4 Intro to Lists [Elementary]](http://www.4clojure.com/problem/4)

```
:a :b :c
```


[#5 Lists: conj [Elementary]](http://www.4clojure.com/problem/5)

```
'(1 2 3 4)
```


[#6 Intro to Vectors [Elementary]](http://www.4clojure.com/problem/6)

```
:a :b :c
```


[#7 Vectors: conj [Elementary]](http://www.4clojure.com/problem/7)

```
[1 2 3 4]
```


[#8 Intro to Sets [Elementary]](http://www.4clojure.com/problem/8)

```
#{:a :b :c :d}
```


[#9 Sets: conj [Elementary]](http://www.4clojure.com/problem/9)

```
2
```


[#10 Intro to Maps [Elementary]](http://www.4clojure.com/problem/10)

```
20
```


[#11 Maps: conj [Elementary]](http://www.4clojure.com/problem/11)

```
{:b 2}
```


[#12 Intro to Sequences [Elementary]](http://www.4clojure.com/problem/12)

```
3
```


[#13 Sequences: rest [Elementary]](http://www.4clojure.com/problem/13)

```
[20 30 40]
```


[#14 Intro to Functions [Elementary]](http://www.4clojure.com/problem/14)

```
8
```


[#15 Double Down [Elementary]](http://www.4clojure.com/problem/15)

```
(partial * 2)
```


[#16 Hello World [Elementary]](http://www.4clojure.com/problem/16)

```
#(str "Hello, " % "!")
```


[#17 Sequences: map [Elementary]](http://www.4clojure.com/problem/17)

```
'(6 7 8)
```


[#18 Sequences: filter [Elementary]](http://www.4clojure.com/problem/18)

```
'(6 7)
```


[#19 Last Element [Easy]](http://www.4clojure.com/problem/19)

```
(fn my-last [coll]
  (if (empty? (rest coll))
    (first coll)
    (my-last (rest coll))))
```


[#20 Penultimate Element [Easy]](http://www.4clojure.com/problem/20)

```
(fn my-last [coll]
  (if (empty? (rest (rest coll)))
    (first coll)
    (my-last (rest coll))))
```


[#21 Nth Element [Easy]](http://www.4clojure.com/problem/21)

```
(fn my-nth [coll n]
  (if (= n 0) 
    (first coll)
    (my-nth (rest coll) (dec n))))
```


[#22 Count a Sequence [Easy]](http://www.4clojure.com/problem/22)

```
(fn my-count [coll]
  (if (empty? coll) 0
    (inc (my-count (rest coll)))))
```


[#23 Reverse a Sequence [Easy]](http://www.4clojure.com/problem/23)

```
(fn my-reverse [coll]
  (if (empty? coll) nil
    (concat (my-reverse (rest coll)) (list (first coll)))))
```


[#24 Sum It All Up [Easy]](http://www.4clojure.com/problem/24)

```
(fn sum [coll]
  (if (empty? coll) 0
    (+ (first coll) (sum (rest coll)))))
```


[#25 Find the odd numbers [Easy]](http://www.4clojure.com/problem/25)

```
(fn filter-odd [coll]
  (if (empty? coll) '()
    (let [elem (first coll)]
      (if (= (mod elem 2) 1)
        (conj (filter-odd (rest coll)) elem)
        (filter-odd (rest coll))))))
```


[#26 Fibonacci Sequence [Easy]](http://www.4clojure.com/problem/26)

```
#(take % ((fn fibgen [n1 n2] (lazy-seq (cons n1 (fibgen n2 (+ n1 n2))))) 1 1))
```


[#27 Palindrome Detector [Easy]](http://www.4clojure.com/problem/27)

```
#(= (seq %) (reverse (seq %)))
```


[#28 Flatten a Sequence [Easy]](http://www.4clojure.com/problem/28)

```
(fn flat [coll]
  (when-let [s (seq coll)]
    (if (coll? (first s))
      (concat (flat (first s)) (flat (rest s)))
      (cons (first s) (flat (rest s))))))
```


[#29 Get the Caps [Easy]](http://www.4clojure.com/problem/29)

```
(fn [s] (apply str (filter #(not= (str %) (clojure.string/lower-case %)) s)))
```


[#30 Compress a Sequence [Easy]](http://www.4clojure.com/problem/30)

```
#(map first (partition-by identity %))
```


[#31 Pack a Sequence [Easy]](http://www.4clojure.com/problem/31)

```
#(partition-by identity %)
```


[#32 Duplicate a Sequence [Easy]](http://www.4clojure.com/problem/32)

```
mapcat #(repeat 2 %)
```


[#33 Replicate a Sequence [Easy]](http://www.4clojure.com/problem/33)

```
(fn [coll times] (mapcat #(repeat times %) coll))
```


[#34 Implement range [Easy]](http://www.4clojure.com/problem/34)

```
#(take (- %2 %1) (iterate inc %1))
```


[#35 Local bindings [Elementary]](http://www.4clojure.com/problem/35)

```
7
```


[#36 Let it Be [Elementary]](http://www.4clojure.com/problem/36)

```
[x 7 y 3 z 1]
```


[#37 Regular Expressions [Elementary]](http://www.4clojure.com/problem/37)

```
"ABC"
```


[#38 Maximum value [Easy]](http://www.4clojure.com/problem/38)

```
#((fn max-iterative [coll current-max] 
    (if (empty? coll) current-max
      (let [possible-new-max (first coll)]
        (if (> possible-new-max current-max) (max-iterative (rest coll) possible-new-max) 
          (max-iterative (rest coll) current-max))))) %& 0)
```


[#39 Interleave Two Seqs [Easy]](http://www.4clojure.com/problem/39)

```
#(mapcat vector %1 %2)
```


[#40 Interpose a Seq [Easy]](http://www.4clojure.com/problem/40)

```
(fn [separator coll] (drop-last (mapcat #(vector % separator) coll)))
```


[#41 Drop Every Nth Item [Easy]](http://www.4clojure.com/problem/41)

```
(fn [coll size] (mapcat #(take (dec size) %) (partition-all size coll)))
```


[#42 Factorial Fun [Easy]](http://www.4clojure.com/problem/42)

```
#(reduce * (range 1 (inc %)))
```


[#43 Reverse Interleave [Medium]](http://www.4clojure.com/problem/43)

```
#(apply map list (partition %2 %1))
```


[#44 Rotate Sequence [Medium]](http://www.4clojure.com/problem/44)

```
(fn go [amount coll]
  (if (< amount 0) (go (+ (count coll) amount) coll)
      (if (= amount 0) coll
          (go (dec amount) (reverse (into '() (conj (vec (drop 1 coll)) (first coll))))))))
```


[#45 Intro to Iterate [Easy]](http://www.4clojure.com/problem/45)

```
'(1 4 7 10 13)
```


[#46 Flipping out [Medium]](http://www.4clojure.com/problem/46)

```
(fn [op] (fn [a b] (op b a)))
```


[#47 Contain Yourself [Easy]](http://www.4clojure.com/problem/47)

```
4
```


[#48 Intro to some [Easy]](http://www.4clojure.com/problem/48)

```
6
```


[#49 Split a sequence [Easy]](http://www.4clojure.com/problem/49)

```
(fn [n coll] (list (vec (take n coll)) (vec (nthrest coll n))))
```


[#50 Split by Type [Medium]](http://www.4clojure.com/problem/50)

```
(fn [coll]
    (vals (group-by type coll)))
```


[#51 Advanced Destructuring [Easy]](http://www.4clojure.com/problem/51)

```
[1 2 3 4 5]
```


[#52 Intro to Destructuring [Elementary]](http://www.4clojure.com/problem/52)

```
[c e]
```


[#53 Longest Increasing Sub-Seq [Hard]](http://www.4clojure.com/problem/53)

```
(fn [coll]
    (letfn [(is-inc? [a e]
              (or (empty? a)
                  (= (inc (last a)) e)))
            (inner-loop [c acc max-acc]
              (if (empty? c) (if (= (count max-acc) 1) [] ; because of [(first c)]
                                 (if (= (last (drop-last 1 coll)) (last max-acc)) ; we miss the last one in the latest if (this is a hack)...
                                   (conj max-acc (last coll))
                                   max-acc))
                  (inner-loop (rest c)
                              (if (is-inc? acc (first c))
                                (conj acc (first c))
                                [(first c)])
                              (if (>= (count acc) (count max-acc))
                                acc
                                max-acc))))]
      (inner-loop coll [] [])))
```


[#54 Partition a Sequence [Medium]](http://www.4clojure.com/problem/54)

```
(fn [x coll]
  (loop [c coll
         acc []]
    (if (or (empty? c)
            (< (count c) x))
      acc
      (recur (drop x c) 
             (conj acc (take x c))))))
```


[#55 Count Occurrences [Medium]](http://www.4clojure.com/problem/55)

```
(fn [coll]
    (into {} (map (fn [[k v]] [k (count v)]) (group-by identity coll))))
```


[#56 Find Distinct Items [Medium]](http://www.4clojure.com/problem/56)

```
(fn [coll]
  (let [step (fn step [xs seen]
               (lazy-seq
                ((fn [[f :as xs] seen]
                   (when-let [s (seq xs)]
                     (if (contains? seen f)
                       (recur (rest s) seen)
                       (cons f (step (rest s) (conj seen f))))))
                 xs seen)))]
    (step coll #{})))
```


[#57 Simple Recursion [Elementary]](http://www.4clojure.com/problem/57)

```
[5 4 3 2 1]
```


[#58 Function Composition [Medium]](http://www.4clojure.com/problem/58)

```
(fn [& fs]
    (fn [& args]
      (let [sf (reverse fs)]
        (if (nth sf 2 nil)
          ((nth sf 2) ((second sf) (apply (first sf) args)))
          ((second sf) (apply (first sf) args))))))
```


[#59 Juxtaposition [Medium]](http://www.4clojure.com/problem/59)

```
(fn [& fs]
    (fn [& args]
      (mapv (fn [f] (apply f args)) fs)))
```


[#60 Sequence Reductions [Medium]](http://www.4clojure.com/problem/60)

```
(fn step
    ([f coll]
     (step f (f (first coll)) (next coll)))
    ([f e coll]
     (if (not-empty coll)
       (lazy-seq (cons e
                       (step f
                             (f e (first coll))
                             (next coll))))
       (list e))))
```


[#61 Map Construction [Easy]](http://www.4clojure.com/problem/61)

```
(fn [ks vs]
    (apply hash-map (interleave ks vs)))
```


[#62 Re-implement Iterate [Easy]](http://www.4clojure.com/problem/62)

```
(fn step [f val]
    (lazy-seq (cons val (step f (f val)))))
```


[#63 Group a Sequence [Easy]](http://www.4clojure.com/problem/63)

```
(fn step
    ([f coll] (step f coll {}))
    ([f coll m]
     (if coll
       (let [k (f (first coll))]
         (step
          f
          (next coll)
          (assoc m k (conj (get m k []) (first coll)))))
       m)))
```


[#64 Intro to Reduce [Elementary]](http://www.4clojure.com/problem/64)

```
+
```


[#65 Black Box Testing [Medium]](http://www.4clojure.com/problem/65)

```
(fn [data]
    (cond (or (= data {}) (:a data))
          :map

          (= (inc (count data)) (count (conj data :data :data :data)))
          :set

          (= (first (conj data 20 21)) 21)
          :list

          (= (last (conj data 20 21)) 21)
          :vector))
```


[#66 Greatest Common Divisor [Easy]](http://www.4clojure.com/problem/66)

```
(fn gcd [a b]
    (if (zero? b)
        a
        (gcd b (mod a b))))
```


[#67 Prime Numbers [Medium]](http://www.4clojure.com/problem/67)

```
(fn [n]
    (take n
          ((fn primes [candidate]
             (lazy-seq
              (if (some #(zero? (mod candidate %)) (range 2 candidate))
                (primes (inc candidate))
                (cons candidate (primes (inc candidate))))))
           2)))
```


[#68 Recurring Theme [Elementary]](http://www.4clojure.com/problem/68)

```
[7 6 5 4 3]
```


[#69 Merge with a Function [Medium]](http://www.4clojure.com/problem/69)

```
(fn [f & ms]
    (let [keyvals (mapcat seq ms)]
      (loop [m     {}
             coll  (next keyvals)
             [k v] (first keyvals)]
        (if v
          (recur (assoc m k (if-let [v2 (get m k)]
                              (f v2 v)
                              v))
                 (next coll)
                 (first coll))
          m))))
```


[#70 Word Sorting [Medium]](http://www.4clojure.com/problem/70)

```
(fn [sentence]
    (sort-by #(clojure.string/lower-case %)
             (-> (clojure.string/replace sentence #"[!.]" "")
                 (clojure.string/split #" "))))
```


[#71 Rearranging Code: -> [Elementary]](http://www.4clojure.com/problem/71)

```
last
```


[#72 Rearranging Code: ->> [Elementary]](http://www.4clojure.com/problem/72)

```
apply +
```


[#73 Analyze a Tic-Tac-Toe Board [Hard]](http://www.4clojure.com/problem/73)

```
(letfn [(transpose [m] (apply mapv vector m))]
    (fn [board]
      (cond (some #(= % [:x :x :x]) (concat board (transpose board)))
            :x

            (some #(= % [:o :o :o]) (concat board (transpose board)))
            :o

            (or (and (= (ffirst board) :x)
                     (= (second (second board)) :x)
                     (= (-> board (nth 2) (nth 2)) :x))
                (and (= (first (last board)) :x)
                     (= (second (second board)) :x)
                     (= (last (first board)) :x)))
            :x

            (or (and (= (ffirst board) :o)
                     (= (second (second board)) :o)
                     (= (-> board (nth 2) (nth 2)) :o))
                (and (= (first (last board)) :o)
                     (= (second (second board)) :o)
                     (= (last (first board)) :o)))
            :o)))
```


[#74 Filter Perfect Squares [Medium]](http://www.4clojure.com/problem/74)

```
(fn [s]
    (letfn [(perfect-square [n]
              (let [root (Math/sqrt n)]
                (= (Math/floor root) root)))]
      (->> (clojure.string/split s #",")
           (map #(Integer/valueOf %))
           (filter perfect-square)
           (interpose ",")
           (apply str))))
```


[#75 Euler's Totient Function [Medium]](http://www.4clojure.com/problem/75)

```
(letfn [(gcd [a b]
            (if (zero? b)
              a
              (gcd b (mod a b))))]
    (fn [n]
      (if (= n 1) 1
          (->> (range 1 n)
               (filter #(= (gcd n %) 1))
               (count)))))
```


[#76 Intro to Trampoline [Medium]](http://www.4clojure.com/problem/76)

```
[1 3 5 7 9 11]
```


[#77 Anagram Finder [Medium]](http://www.4clojure.com/problem/77)

```
(fn [words]
    (->> (group-by sort words)
         (vals)
         (filter #(> (count %) 1))
         (map set)
         (set)))
```


[#78 Reimplement Trampoline [Medium]](http://www.4clojure.com/problem/78)

```
(fn [f & args]
    (loop [res (apply f args)]
      (if (fn? res)
        (recur (res))
        res)))
```


[#79 Triangle Minimal Path [Hard]](http://www.4clojure.com/problem/79)

```
(fn [triangle]
    (let [row (last triangle)]
      (if (= (count row) 1)
        (first row)
        (recur (concat (drop-last 2 triangle)
                       [(mapv (fn [a [b c]] (min (+ a b) (+ a c)))
                              (last (drop-last triangle))
                              (partition 2 1 (last triangle)))])))))
```


[#80 Perfect Numbers [Medium]](http://www.4clojure.com/problem/80)

```
(fn [x]
    (letfn [(divisors [n] (filter #(integer? (/ n %)) (range 1 n)))
            (perfect? [n] (= n (apply + (divisors n))))]
      (perfect? x)))
```


[#81 Set Intersection [Easy]](http://www.4clojure.com/problem/81)

```
(fn [s1 s2]
    (letfn [(dups [c] (for [[n freq] (frequencies c)
                            :when (> freq 1)]
                        n))]
      (set (dups (concat s1 s2)))))
```


[#82 Word Chains [Hard]](http://www.4clojure.com/problem/82)

```
TODO
```


[#83 A Half-Truth [Easy]](http://www.4clojure.com/problem/83)

```
TODO
```


[#84 Transitive Closure [Hard]](http://www.4clojure.com/problem/84)

```
TODO
```


[#85 Power Set [Medium]](http://www.4clojure.com/problem/85)

```
TODO
```


[#86 Happy numbers [Medium]](http://www.4clojure.com/problem/86)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[#88 Symmetric Difference [Easy]](http://www.4clojure.com/problem/88)

```
TODO
```


[#89 Graph Tour [Hard]](http://www.4clojure.com/problem/89)

```
TODO
```


[#90 Cartesian Product [Easy]](http://www.4clojure.com/problem/90)

```
TODO
```


[#91 Graph Connectivity [Hard]](http://www.4clojure.com/problem/91)

```
TODO
```


[#92 Read Roman numerals [Hard]](http://www.4clojure.com/problem/92)

```
TODO
```


[#93 Partially Flatten a Sequence [Medium]](http://www.4clojure.com/problem/93)

```
TODO
```


[#94 Game of Life [Hard]](http://www.4clojure.com/problem/94)

```
TODO
```


[#95 To Tree, or not to Tree [Easy]](http://www.4clojure.com/problem/95)

```
TODO
```


[#96 Beauty is Symmetry [Easy]](http://www.4clojure.com/problem/96)

```
TODO
```


[#97 Pascal's Triangle [Easy]](http://www.4clojure.com/problem/97)

```
TODO
```


[#98 Equivalence Classes [Medium]](http://www.4clojure.com/problem/98)

```
TODO
```


[#99 Product Digits [Easy]](http://www.4clojure.com/problem/99)

```
TODO
```


[#100 Least Common Multiple [Easy]](http://www.4clojure.com/problem/100)

```
TODO
```


[#101 Levenshtein Distance [Hard]](http://www.4clojure.com/problem/101)

```
TODO
```


[#102 intoCamelCase [Medium]](http://www.4clojure.com/problem/102)

```
TODO
```


[#103 Generating k-combinations [Medium]](http://www.4clojure.com/problem/103)

```
TODO
```


[#104 Write Roman Numerals [Medium]](http://www.4clojure.com/problem/104)

```
TODO
```


[#105 Identify keys and values [Medium]](http://www.4clojure.com/problem/105)

```
TODO
```


[#106 Number Maze [Hard]](http://www.4clojure.com/problem/106)

```
TODO
```


[#107 Simple closures [Easy]](http://www.4clojure.com/problem/107)

```
TODO
```


[#108 Lazy Searching [Medium]](http://www.4clojure.com/problem/108)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[#110 Sequence of pronunciations [Medium]](http://www.4clojure.com/problem/110)

```
TODO
```


[#111 Crossword puzzle [Hard]](http://www.4clojure.com/problem/111)

```
TODO
```


[#112 Sequs Horribilis [Medium]](http://www.4clojure.com/problem/112)

```
TODO
```


[#113 Making Data Dance [Hard]](http://www.4clojure.com/problem/113)

```
TODO
```


[#114 Global take-while [Medium]](http://www.4clojure.com/problem/114)

```
TODO
```


[#115 The Balance of N [Medium]](http://www.4clojure.com/problem/115)

```
TODO
```


[#116 Prime Sandwich [Medium]](http://www.4clojure.com/problem/116)

```
TODO
```


[#117 For Science! [Hard]](http://www.4clojure.com/problem/117)

```
TODO
```


[#118 Re-implement Map [Easy]](http://www.4clojure.com/problem/118)

```
TODO
```


[#119 Win at Tic-Tac-Toe [Hard]](http://www.4clojure.com/problem/119)

```
TODO
```


[#120 Sum of square of digits [Easy]](http://www.4clojure.com/problem/120)

```
TODO
```


[#121 Universal Computation Engine [Medium]](http://www.4clojure.com/problem/121)

```
TODO
```


[#122 Read a binary number [Easy]](http://www.4clojure.com/problem/122)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[#124 Analyze Reversi [Hard]](http://www.4clojure.com/problem/124)

```
TODO
```


[#125 Gus' Quinundrum [Hard]](http://www.4clojure.com/problem/125)

```
TODO
```


[#126 Through the Looking Class [Easy]](http://www.4clojure.com/problem/126)

```
TODO
```


[#127 Love Triangle [Hard]](http://www.4clojure.com/problem/127)

```
TODO
```


[#128 Recognize Playing Cards [Easy]](http://www.4clojure.com/problem/128)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[#130 Tree reparenting [Hard]](http://www.4clojure.com/problem/130)

```
TODO
```


[#131 Sum Some Set Subsets [Medium]](http://www.4clojure.com/problem/131)

```
TODO
```


[#132 Insert between two items [Medium]](http://www.4clojure.com/problem/132)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[#134 A nil key [Elementary]](http://www.4clojure.com/problem/134)

```
#(and (contains? %2 %1) (nil? (%1 %2)))
```


[#135 Infix Calculator [Easy]](http://www.4clojure.com/problem/135)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[#137 Digits and bases [Medium]](http://www.4clojure.com/problem/137)

```
TODO
```


[#138 Squares Squared [Hard]](http://www.4clojure.com/problem/138)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[#140 Veitch, Please! [Hard]](http://www.4clojure.com/problem/140)

```
TODO
```


[#141 Tricky card games [Medium]](http://www.4clojure.com/problem/141)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[#143 dot product [Easy]](http://www.4clojure.com/problem/143)

```
TODO
```


[#144 Oscilrate [Medium]](http://www.4clojure.com/problem/144)

```
(fn [val & fns]
    (let [fns (cycle fns)]
      (reductions (fn [acc f] (f acc)) val fns)))
```


[#145 For the win [Elementary]](http://www.4clojure.com/problem/145)

```
TODO
```


[#146 Trees into tables [Easy]](http://www.4clojure.com/problem/146)

```
TODO
```


[#147 Pascal's Trapezoid [Easy]](http://www.4clojure.com/problem/147)

```
TODO
```


[#148 The Big Divide [Medium]](http://www.4clojure.com/problem/148)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[#150 Palindromic Numbers [Medium]](http://www.4clojure.com/problem/150)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[#152 Latin Square Slicing [Hard]](http://www.4clojure.com/problem/152)

```
TODO
```


[#153 Pairwise Disjoint Sets [Easy]](http://www.4clojure.com/problem/153)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[#156 Map Defaults [Elementary]](http://www.4clojure.com/problem/156)

```
TODO
```


[#157 Indexing Sequences [Easy]](http://www.4clojure.com/problem/157)

```
TODO
```


[#158 Decurry [Medium]](http://www.4clojure.com/problem/158)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


[  []](http://www.4clojure.com/problem/)

```
TODO
```


