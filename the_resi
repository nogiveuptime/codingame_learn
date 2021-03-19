package main

import (
    "fmt"
)

var morsedict = map[rune]string{
	'A': ".-",
	'B': "-...",
	'C': "-.-.",
	'D': "-..",
	'E': ".",
	'F': "..-.",
	'G': "--.",
	'H': "....",
	'I': "..",
	'J': ".---",
	'K': "-.-",
	'L': ".-..",
	'M': "--",
	'N': "-.",
	'O': "---",
	'P': ".--.",
	'Q': "--.-",
	'R': ".-.",
	'S': "...",
	'T': "-",
	'U': "..-",
	'V': "...-",
	'W': ".--",
	'X': "-..-",
	'Y': "-.--",
	'Z': "--..",
}

var morses = map[string]int{}
/**
 * Auto-generated code below aims at helping you parse
 * the standard input according to the problem statement.
 **/
func toMorse(word string) (morse string) {
    for i := 0; i < len(word); i++ {
        morse += morsedict[rune(word[i])]
    }
    
    return
}

func getAllPossibleMorse(init int, L string, mem map[int]int) (result int) {
    if init == len(L) {return 1}

    if _, ok := mem[init]; ok {
        return mem[init]
    }
	
    for i := 1; i <= 80 && init + i <= len(L); i++ {
	if x, ok := morses[string(L[init:init+i])]; ok {
		result += x * getAllPossibleMorse(init + i, L, mem)
	}
    }

    mem[init] = result

    return
}

func main() {
    var L string
    fmt.Scan(&L)
    
    var N int
    fmt.Scan(&N)
    
    for i := 0; i < N; i++ {
        var W string
        fmt.Scan(&W)

	morses[toMorse(W)]++
    }
    
    result := getAllPossibleMorse(0, L, map[int]int{})

    fmt.Println(result)

}
