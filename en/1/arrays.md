---
title: Tablice
actions: ['Sprawdż Odpowiedż', 'wskazówka']
requireLogin: true
material:
  editor:
    language: sol
    startingCode: |
      pragma solidity >=0.5.0 <0.6.0;

      contract ZombieFactory {

          uint dnaDigits = 16;
          uint dnaModulus = 10 ** dnaDigits;

          struct Zombie {
              string name;
              uint dna;
          }

          // zacznij tutaj

      }
    answer: >
      pragma solidity >=0.5.0 <0.6.0;


      contract ZombieFactory {

          uint dnaDigits = 16;
          uint dnaModulus = 10 ** dnaDigits;

          struct Zombie {
              string name;
              uint dna;
          }

          Zombie[] public zombies;

      }
---

//When you want a collection of something, you can use an **_array_**. There are two types of arrays in Solidity: **_fixed_** arrays and **_dynamic_** arrays://
Gdy chcesz utworzyć kolekcję czegoś, możesz użyć array (tablicy). W Solidity są dwa typy tablic: stałe i dynamiczne:


```
// Array with a fixed length of 2 elements:
// Tablica o stałej długości 2 elementów:
uint[2] fixedArray;

// another fixed Array, can contain 5 strings:
// kolejna tablica stała, może zawierać 5 stringów:
string[5] stringArray;

// a dynamic Array - has no fixed size, can keep growing:
// tablica dynamiczna - nie ma stałego rozmiaru, może się powiększać:
uint[] dynamicArray;
```

You can also create an array of **_structs_**. Using the previous chapter's `Person` struct:
Możesz również utworzyć tablicę struktur (structs). Korzystając z 'Person', czyli struktury z poprzedniego rozdziału:

```
Person[] people; // dynamic Array, we can keep adding to it
// tablica dynamiczna, możemy do niej ciągle dodawać elementy
```

Remember that state variables are stored permanently in the blockchain? So creating a dynamic array of structs like this can be useful for storing structured data in your contract, kind of like a database.

Pamiętaj, że zmienne stanu są przechowywane na stałe w blockchainie. Utworzenie dynamicznej tablicy struktur w ten sposób może być przydatne do przechowywania danych strukturalnych w kontrakcie, trochę jak w bazie danych.

## Publiczne Tablice

You can declare an array as `public`, and Solidity will automatically create a **_getter_** method for it. The syntax looks like:
Możesz zadeklarować tablicę jako public, a Solidity automatycznie utworzy dla niej getter (metodę pobierającą). Składnia wygląda tak:
```

Other contracts would then be able to read from, but not write to, this array. So this is a useful pattern for storing public data in your contract.
Inne kontrakty będą mogły odczytywać tę tablicę, ale nie będą mogły do niej pisać. Jest to więc przydatny wzorzec do przechowywania publicznych danych w kontrakcie.

# Sprawdź to w praktyce

We're going to want to store an army of zombies in our app. And we're going to want to show off all our zombies to other apps, so we'll want it to be public.
Chcemy przechowywać armię zombie w naszej aplikacji. I chcemy pokazać wszystkie nasze zombie innym aplikacjom, więc będziemy chcieli, żeby tablica była publiczna.

1. Create a public array of `Zombie` **_structs_**, and name it `zombies`.
1. 111Utwórz publiczną tablicę struktur Zombie i nazwij ją zombies.
