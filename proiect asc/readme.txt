Echipa noastră: 
	Nume: XorT11am
	Membrii:
		- Florea Mădălin-Alexandru (grupa 143)
		- Lung Alexandra (grupa 143)
		- Gheorghe Robert-Mihai (grupa 143)

Cerința 1: Scrieți scripturi python encrypt.py/decrypt.py care iau ca parametru în linia de comandă o cheie și un fișier și realizează criptarea/decriptarea XOR folosind cheia dată. Programul va folosi cheia pentru a cripta conținutul fișierului.

Cum se utilizează script-urile:
 	Mediul de lucru
		- Python 3.10.0
	Instrucțiuni pentru a rula in Windows
		- se deschide CMD-ul / terminalul
		- se accesează locația proiectului
		- se introduc următoarele comenzi:
			python encrypt.py <parola> input.txt output                  -> (pentru criptare)
			python decrypt.py <parola> output input_recuperat.txt        -> (pentru decriptare)
	
ATENȚIE!!! La introducerea comenzilor, în loc de <parola> va fi scrisă direct cheia folosită pentru criptare / decriptare, fără '<' , respectiv '>'.
Aceiași pași se urmează și pe Ubuntu, dar comenzile conțin "python3" in loc de "python", deci:
	python3 encrypt.py <parola> input.txt output
	python3 decrypt.py <parola> output input_recuperat.txt

Documentație:
https://docs.python.org/3/library/stdtypes.html
Sursa textului din input.txt: https://ro.m.wikisource.org/wiki/Ion/Glasul_p%C4%83m%C3%A2ntului

------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Numele echipei adverse: The Robotors
Link GitHub către proiectul lor: https://github.com/alex2209alex/proiectAsc
Cheia pe care au folosit-o: parola121alorap

Cerința 2: Aflați cheia cu care a fost criptat fișierul output al echipei adverse.

Partea 1: Folosiți fișierul input.txt, output și fișierele sursă de pe pagina github a echipei adverse pentru a afla cheia (dacă cheia este disponibilă undeva pe pagina github a echipei adverse, folosiți-o; folosiți-vă de orice mijloace tehnice pentru a descoperi cheia).
	-> Pentru a rezolva această cerință, ne-am folosit de scriptul cerinta2partea1.py. Pe măsură ce parcurgem câte un caracter din output-ul, respectiv input-ul adversarilor, reținem într-un string parola obținută prin XOR-area acestora și îl trecem prin funcția de hash. Dacă hash-ul parolei noastre coincide cu cel din encrypt-ul echipei adverse, afișăm parola.

Pentru fiecare lungime între 10 și 15 caractere și fiecare poziție din parolă, verificăm fiecare caracter care poate exista în parolă prin citirea din fișierul de output și vedem dacă XOR-at cu acel caracter citit de poziția x dă un caracter valid care poate fi regăsit în input. Ulterior, reținem toate posibilitățile, apoi generăm toate parolele posibile prin produs cartezian și le comparăm cu hash-ul din encrypt.

Partea 2: Folosiți fișierul output și fișierele sursă de pe pagina github a echipei adverse pentru a afla cheia (NU aveți voie să folosiți input.txt).
	-> Pentru a rezolva această cerință, ne-am folosit de scriptul cerinta2partea2.py. Pentru fiecare lungime posibilă a parolei (de la 10 la 15), găsim toate caracterele posibile pentru fiecare poziție din parolă*. Cu aceste caractere facem produs cartezian pentru a afla posibilele parole, pe care le trecem prin funcția de hash și le comparăm cu hash-ul din encrypt-ul oponenților.
*Pentru acest lucru, luăm toate caracterele care pot apărea în parolă (litere mici, litere mari și cifre) și verificăm dacă XOR-ate cu caracterele de pozițiile corespunzătoare din outputul adversarilor, obținem un caracter inteligibil (litere mari, litere mici, semne de punctuație, cifre, spații sau newline).
