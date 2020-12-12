man(george).
man(john).
man(robert).

woman(barbara).
woman(christine).
woman(yolanda).

members([],_).
members([M|Ms],Xs) :- select(M,Xs,Ys),members(Ms,Ys).

clue1(House) :-
    members([[P,kitchen,_],[_,_,rope],[_,_,knife],[_,_,bag],[_,_,firearm]],House),
    man(P).
clue2(House) :-
    member([barbara,study,_],House), member([yolanda,bathroom,_],House).
clue2(House) :-
    member([barbara,bathroom,_],House), member([yolanda,study,_],House).
clue3(House) :-
    members([[_,_,bag],[barbara,_,_],[george,_,_]],House),
    members([[_,_,bag],[_,bathroom,_],[_,dining_room,_]],House).
clue4(House) :-
    members([[P,study,rope]],House),woman(P).
clue5(House) :-
    members([[john,living_room,_]],House).
clue5(House) :-
    members([[george,living_room,_]],House).
clue6(House) :-
    members([[_,_,knife],[_,dining_room,_]],House).
clue7(House) :-
    members([[yolanda,_,_],[_,study,_],[_,pantry,_]],House).
clue8(House) :-
    member([george,_,firearm],House).
clue9(House,P) :-
    members([[P,pantry,gas]],House).

solve(X) :-
    House = [[_,bathroom,_],[_,dining_room,_],[_,kitchen,_],[_,living_room,_],
             [_,pantry,_],[_,study,_]],
    clue1(House),
    clue2(House),
    clue3(House),
    clue4(House),
    clue5(House),
    clue6(House),
    clue7(House),
    clue8(House),
    clue9(House,X),
    members([[george,_,_],[john,_,_],[robert,_,_],[barbara,_,_],[christine,_,_],
             [yolanda,_,_]],House),
    members([[_,_,bag],[_,_,firearm],[_,_,gas],[_,_,knife],[_,_,poison],
             [_,_,rope]],House),
    write(House),
    true.
