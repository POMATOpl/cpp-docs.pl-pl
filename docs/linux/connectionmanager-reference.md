---
title: ConnectionManager — dokumentacja
description: Jak zarządzać zdalnymi połączeniami SSH za pomocą narzędzia wiersza polecenia.
ms.date: 10/7/2020
f1_keywords:
- ConnectionManager
helpviewer_keywords:
- ConnectionManager program
ms.openlocfilehash: 065a2cf6d6a2fe7d7e418299255c5bbf1f2bf753
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/29/2020
ms.locfileid: "92921623"
---
# <a name="connectionmanager-reference"></a>ConnectionManager — dokumentacja

::: moniker range="<=msvc-150"

ConnectionManager.exe jest dostępny w programie Visual Studio 2019 w wersji 16,5 lub nowszej.

::: moniker-end

::: moniker range="msvc-160"

ConnectionManager.exe to narzędzie wiersza polecenia do zarządzania połączeniami zdalnego tworzenia poza programem Visual Studio. Jest to przydatne w przypadku zadań, takich jak inicjowanie obsługi nowej maszyny deweloperskiej. Można też użyć go do skonfigurowania programu Visual Studio na potrzeby ciągłej integracji. Można go użyć w oknie wiersz polecenia dla deweloperów. Aby uzyskać więcej informacji na temat wiersz polecenia dla deweloperów, zobacz Korzystanie z zestawu [narzędzi Microsoft C++ w wierszu polecenia](../build/building-on-the-command-line.md).

ConnectionManager.exe jest dostępny w programie Visual Studio 2019 w wersji 16,5 lub nowszej. Jest to część rozwoju systemu **Linux z obciążeniem języka C++** w Instalator programu Visual Studio. Jest ona również instalowana automatycznie po wybraniu składnika **Menedżera połączeń** w instalatorze. Jest on instalowany w *% VCIDEInstallDir% \\ Linux \\ bin \\ ConnectionManagerExe \\ConnectionManager.exe* .

Funkcje ConnectionManager.exe są również dostępne w programie Visual Studio. Aby zarządzać połączeniami zdalnego tworzenia w IDE, na pasku menu wybierz **Narzędzia**  >  **Opcje** , aby otworzyć okno dialogowe Opcje. W oknie dialogowym Opcje wybierz pozycję Menedżer połączeń **między platformami**  >  **Connection Manager** .

## <a name="syntax"></a>Składnia

> **`ConnectionManager.exe`***polecenie* \[ *argumenty* ] \[ *Opcje* ]

### <a name="commands-and-arguments"></a>Polecenia i argumenty

- **`add`***\@ host użytkownika* \[ **`--port`** *port* ] \[ **`--password`** *password* hasło \[ ] **`--privatekey`** *privatekey_file* ]

  Uwierzytelnia i dodaje nowe połączenie. Domyślnie używa on portu 22 i uwierzytelniania hasła. (Zostanie wyświetlony monit o wprowadzenie hasła). Użyj obu **-`-password`** i, **`--privatekey`** Aby określić hasło dla klucza prywatnego.

- **`remove`**\[ *connection_id* \| *port \@ hosta użytkownika* connection_id \[ **`--port`** *port* ]]

  Usuwa połączenie. Jeśli nie określono żadnych argumentów, zostanie wyświetlony monit o określenie, które połączenie ma zostać usunięte.
  
- **`modify`**\[ *domyślny* \| *connection_id* \| *port \@ hosta użytkownika* connection_id \[ **`--port`** *port* ]] \[ **`--property`** *klucz = wartość* ]

  Definiuje lub modyfikuje Właściwość połączenia. \
  Jeśli *wartość* jest pusta, *klucz* właściwości zostanie usunięty. \
  Jeśli uwierzytelnianie nie powiedzie się, nie zostaną wprowadzone żadne zmiany. \
  Jeśli nie określono połączenia (co jest *Domyślnie* określone powyżej), używane jest domyślne połączenie zdalne użytkownika.

- **`remove-all`**

  Usuwa wszystkie przechowywane połączenia.
  
- **`clean`**

  Usuwa pamięć podręczną nagłówków dla połączeń, które już nie istnieją. 

- **`list`** \[**`--properties`** ]

  Wyświetla informacje, identyfikatory i właściwości wszystkich przechowywanych połączeń. 

- **`help`**

  Wyświetla ekran pomoc.

- **`version`**

  Wyświetla informacje o wersji.

### <a name="options"></a>Opcje

- **`-q`** , **`--quiet`**

  Uniemożliwia wyjście do `stdout` lub `stderr` .

- **`--no-prompt`**

  Niepowodzenie zamiast monitu, w razie potrzeby.

- **`--no-verify`**

  Dodaj lub zmodyfikuj połączenie bez uwierzytelniania.

- **`--file`***Nazwa pliku*

  Odczytaj informacje o połączeniu z podanej *nazwy pliku* .

- **`--no-telemetry`**

  Wyłącz wysyłanie danych użycia z powrotem do firmy Microsoft. Dane użycia są zbierane i wysyłane do firmy Microsoft, chyba że **`--no-telemetry`** Flaga zostanie przeniesiona.  

- **`-n`** , **`--dry-run`**

  Wykonuje polecenie w postaci suchego przebiegu.
 
- **`--p`**

  Analogicznie jak **`--password`** .

- **`-i`**

  Analogicznie jak **`--privatekey`** .

## <a name="examples"></a>Przykłady

To polecenie dodaje połączenie dla użytkownika o nazwie "User" na hoście lokalnym. Połączenie używa pliku klucza do uwierzytelniania, znaleziono w *% USERPROFILE% \. ssh \ id_rsa* .

```cmd
ConnectionManager.exe add user@127.0.0.1 --privatekey "%USERPROFILE%\.ssh\id_rsa"
```

To polecenie usuwa połączenie z IDENTYFIKATORem 1975957870 z listy połączeń.

```cmd
ConnectionManager.exe remove 1975957870
```

To polecenie zastępuje wybór powłoki dla połączenia z IDENTYFIKATORem połączenia 21212121. Obsługiwane powłoki: **`sh, csh, bash, tcsh, ksh, zsh, dash`** . Jeśli powłoka znaleziona w systemie Linux nie jest obsługiwana, wrócimy do jawnego użycia **`sh`** dla wszystkich poleceń.

```cmd
ConnectionManager.exe modify 21212121 --property shell=csh
```

## <a name="see-also"></a>Zobacz także

[Nawiązywanie połączenia z docelowym systemem Linux w programie Visual Studio](connect-to-your-remote-linux-computer.md)

::: moniker-end