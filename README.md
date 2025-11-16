# Battaglia Navale
Per la creazione del gioco Battaglia Navale in Python, bisogna prima capire come procedere.

Steps:

creazione di 2 matrici (griglie 10*10) = lista nella lista

creazione di una classe: insieme di oggetti con le stesse caratteristiche 
    classe: griglia, numero di navi e quanto lunghe
    
oggetti: i 2 campi di battaglia
N.B! Le navi, non devono sovrapporsi (non si possono ripetere le caselle che sono già state utilizzate)

funzione “def__init__(self, N, L):” —> definisce il costruttore, che permette di costruire gli oggetti della classe


## Codice più facile con navi lughe 1:

import random


class Campo:

    def __init__(self,n,navi):
    
        self.navi = navi
        
        self.matr =[]
        
        for i in range(n):
        
            self.matr.append([])
            
            for j in range (n):
            
                self.matr[i].append(0)
       
    def popola_random(self):
        for nave in self.navi:
            x = random.randint(0, 9)
            y = random.randint(0, 9)


            while self.matr[x][y] == 'X':
                x = random.randint(0, 9)
                y = random.randint(0, 9)
            self.matr[x][y] = 'X'
   
    def printcampo(self):
            for i in range(len(self.matr)):
                s = ''
                for j in range(len(self.matr)):
                    s += str(self.matr[i][j])
                print(s)

if __name__ == "__main__":

   c = Campo (10, [1,1,1,1])
   
   c.popola_random()
   
   c.printcampo()


Se invece si vuole aumentare la difficoltà si crea il codice con una delle 4 navi lunga 4.
   
## Codice più difficile con una nave lunga 4 e tre lunghe 1
Il verso in cui posizioniamo le navi è verso il basso.

Prima di scrivere il codice dobbiamo accertarci di due cose.
### CONTROLLO 1
per ogni nave empty=true

per ogni i in range (per la lunghezza della nave) scelgo x e y

la domanda da porsi è: posso usare questa coppia? ci sono spazi vuoti? Se si —> la coppia viene scritta nella matrice

Altrimenti se la casella è già occupata bisogna prendere un’altra coppia (x,y)

N.B!: y deve essere allungabile di 3 (per colpire gli altri punti)


## CONTROLLO 2
LUNGHEZZA MATRICE - LUNGHEZZA NAVE = 10 - 4 = 6 —--> y non deve essere maggiore di 6 sennò esce fuori dalla griglia

se invece y > 6 (ELSE) bisogna ricalcolare x e y, così il ciclo si ripete

# INCONTRO 13/11/15
Cosa siamo riusciti a fare?

Versione 0.1= abbiamo creato il costruttore della classe

griglie da 10*10

lunghezza navi 

numero navi

verifica degli spazi vuoti o occupati da X

prossima modifica: aggiungere la variabile  orizzontale e verticale
			             e riangolazione (verso alto, basso) oppure random (verso alto, basso)

step evolutivo : funzione che da all’utente la scelta della nave (es: da casella C6 a C8)
                  e funzionalità del gioco (colpito o affondato)

obiettivo finale: client server (+ giocatori umani, senza bot)





