add(3, 11, 22, 33)

push 33
push 22
push 11
push 3
call add
add esp, 4*4

esp -> 33

esp -> 22
       33

esp -> 11
       22
       33

esp -> 3
ap  -> 11
       22
       33

&argc -> 3
ap    -> 11
         22
         33