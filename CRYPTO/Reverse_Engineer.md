# [Reverse Engineer] - [Kategori, Crypto]
**Poeng:** 550
**Vanskelighetsgrad:** Medium
**Konkurranse:** CTFkom 02.09.2026

## Beskrivelse
Oppgaven ga ut et Python script ('challenge.py') som krypterer flagget, samt en kryptert output-streng. Målet er å reversere krypteringsprosessen for å gjenopprette det opprinnelige flagget.
Tipset i oppgaven var: 
> Knowing what bits/binary/ASCII is and how to convert will help you a lot!
 
Dette antydet at løsningen involverte binær- og ASCII-konvertering.

## Det gitte scriptet
```python
flag = b'CTFKom{?????????????????????}'
 
def encrypt(FLAG):
    encrypted = []
    plaintext_bits = "".join([bin(i)[2:].zfill(8) for i in FLAG])
    for b in plaintext_bits:
        encrypted.append(b)
    encrypted.reverse()
    return "".join(encrypted)
 
print(encrypt(flag))
```

Og output-strengen som skulle dekrypteres:
```
1011111011100110011101101001011001001110110011001010011001110110100011001110011001110110110011001111101010100110110011100100111011001100011011101100110001001110111110100011011000101100110011000100111011011110101101101111011011010110011000100010101011000010
```

## Analyse
`encrypt()` gjør tre ting: konverterer hver byte i flagget til 8-bits binær, slår sammen alle bitene til en lang streng og reverserer hele strengen. Siden reversering er sin egen invers, holder det å reversere strengen tilbake
for å få bitene i riktig rekkefølge igjen. Deretter deles strengen opp i
grupper på 8 bits, og hver gruppe konverteres til et ASCII-tegn med `chr()`.

## Løsningsscript
 
```python
encrypted_output = "1011111011100110011101101001011001001110110011001010011001110110100011001110011001110110110011001111101010100110110011100100111011001100011011101100110001001110111110100011011000101100110011000100111011011110101101101111011011010110011000100010101011000010"
 
# Steg 1: Reverser hele bit-strengen tilbake til original rekkefølge
reversed_bits = encrypted_output[::-1]
 
# Steg 2 og 3: Del opp i 8-bits grupper og konverter hver til et ASCII-tegn
flag = "".join(
    chr(int(reversed_bits[i:i+8], 2))
    for i in range(0, len(reversed_bits), 8)
)
 
print(flag)
```

## Resultat
 
Å kjøre scriptet gir følgende output:
 
```
CTFkom{r34l_r3v3rse_3ng1ne3ring}
```

**Flagg: `CTFkom{r34l_r3v3rse_3ng1ne3ring}`**
