---
title: Właściwości C/C++ (Linux C++)
ms.date: 10/14/2020
description: Opisuje opcje kompilacji systemu Linux na stronie właściwości programu Visual Studio C/C++
ms.assetid: 4bb8894b-c874-4a68-935e-b127d54e484f
f1_keywords: []
ms.openlocfilehash: 0840327b30d94b4845adef7788fd73f4e797775f
ms.sourcegitcommit: f19f02f217b80804ab321d463c76ce6f681abcc6
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 10/19/2020
ms.locfileid: "92176233"
---
# <a name="cc-properties-linux-c"></a>Właściwości C/C++ (Linux C++)

::: moniker range="vs-2015"

Obsługa systemu Linux jest dostępna w programie Visual Studio 2017 i nowszych.

::: moniker-end

::: moniker range=">=vs-2017"

## <a name="general"></a>Ogólne

| Właściwość | Opis | Choices |
|--|--|--|
| Dodatkowe katalogi dołączane | Określa co najmniej jeden katalog do dodania do ścieżki dołączania. Użyj średników do rozdzielenia wielu katalogów. (-I \[ ścieżka]). |
| Format informacji o debugowaniu | Określa typ informacji o debugowaniu generowanych przez kompilator. | **Brak** — nie tworzy informacji o debugowaniu, dzięki czemu kompilacja może być szybsza.<br/>**Minimalne informacje debugowania** — generowanie minimalnych informacji o debugowaniu.<br/>**Pełne informacje o debugowaniu (DWARF2)** — generują informacje debugowania DWARF2.<br/> |
| Nazwa pliku obiektu | Określa nazwę do przesłaniania domyślnej nazwy pliku obiektu. Może to być nazwa pliku lub katalogu. (-o [nazwa]). |
| Poziom ostrzeżeń | Wybiera, jak ścisłość kompilator ma mieć wpływ na błędy kodu.  Dodaj inne flagi bezpośrednio do **dodatkowych opcji**. (/w,/Weverything). | Wyłącz **wszystkie ostrzeżenia** — wyłącza wszystkie ostrzeżenia kompilatora.<br/>**Włącz wszystkie ostrzeżenia** — włącza wszystkie ostrzeżenia, w tym wyłączone domyślnie.<br/> |
| Traktuj ostrzeżenia jako błędy | Traktuje wszystkie ostrzeżenia kompilatora jako błędy. W przypadku nowego projektu najlepiej jest używać/Werror we wszystkich kompilacjach. Usuń wszystkie ostrzeżenia, aby upewnić się, że wady kodu są trudne do znalezienia. |
| Dodatkowe ostrzeżenia dotyczące języka C | Definiuje zestaw dodatkowych komunikatów ostrzegawczych. |
| Dodatkowe ostrzeżenia dotyczące języka C++ | Definiuje zestaw dodatkowych komunikatów ostrzegawczych. |
| Włącz tryb pełny | Gdy tryb informacji pełnej jest włączony, program drukuje więcej informacji umożliwiających zdiagnozowanie kompilacji. |
| Kompilator języka C | Określa program do wywołania podczas kompilacji źródłowych plików języka C lub ścieżkę do kompilatora języka C w systemie zdalnym. |
| Kompilator C++ | Określa program do wywołania podczas kompilacji źródłowych plików języka C++ lub ścieżkę do kompilatora języka C++ w systemie zdalnym. |
| Limit czasu kompilacji | Limit czasu kompilacji zdalnej (w milisekundach). |
| Kopiuj pliki obiektów | Określa, czy mają być kopiowane skompilowane pliki obiektów z systemu zdalnego na maszynę lokalną. |
| Maksymalna liczba równoległych zadań kompilacji | Liczba procesów, które mają zostać utworzone równolegle podczas kompilacji. Wartość domyślna to 1. W przypadku korzystania z podsystemu Windows dla systemu Linux (WSL) w wersji 1 limit wynosi 64. |
| Weryfikuj architekturę | Określ, czy chcesz sprawdzić, czy platforma, do której odwołuje się projekt, jest zgodna z systemem zdalnym.|
| Włącz Sanitizer adresów | Skompiluj program z adresem Sanitizer, który jest szybkim detektorem błędów pamięci, który może znaleźć problemy z pamięcią środowiska uruchomieniowego, takie jak użycie-za darmo, i przeprowadzenie kontroli poza granicami.|

## <a name="optimization"></a>Optymalizacja

| Właściwość | Opis | Choices |
|--|--|--|
| Optymalizacja | Określa poziom optymalizacji aplikacji. | Optymalizacja **niestandardowa** .<br/>**Wyłączone** — wyłączenie optymalizacji.<br/>**Minimalizuj rozmiar** — Optymalizuj pod kątem rozmiaru.<br/>**Maksymalizuj szybkość** — Optymalizuj szybkość.<br/>**Pełna optymalizacja** — kosztowna Optymalizacja. |
| Jednostrictne aliasowanie | Przyjmuje zasady najdokładniejszych aliasów.  Obiekt jednego typu nigdy nie przyjmuje się, że ma taki sam adres jak obiekt innego typu. |
| Odwrócenie pętli | Wycofuje pętle, aby przyspieszyć działanie aplikacji dzięki zmniejszeniu liczby wykonywanych gałęzi przy użyciu kosztu większego rozmiaru kodu. |
| Optymalizacja czasu konsolidacji | Włącza optymalizacje między procedurami, umożliwiając Optymalizatorowi przeglądanie plików obiektów w aplikacji. |
| Pomiń wskaźnik ramki | Pomija tworzenie wskaźników ramek na stosie wywołań. |
| Brak wspólnych bloków | Przydziela nawet Niezainicjowane zmienne globalne w sekcji danych pliku obiektu, zamiast generować je jako bloki wspólne. |

## <a name="preprocessor"></a>Preprocesor

| Właściwość | Opis |
|--|--|
| Definicje preprocesora | Definiuje symbole przetwarzania wstępnego dla pliku źródłowego. (-D) |
| Usuń Definicje preprocesora | Określa co najmniej jedną definicję preprocesora.  (-U — \[ makro]) |
| Usuń wszystkie Definicje preprocesora | Definiuje wszystkie zdefiniowane wcześniej wartości preprocesora.  (-undef) |
| Pokaż zawiera | Generuje listę plików dołączanych z danymi wyjściowymi kompilatora.  (-H) |

## <a name="code-generation"></a>Generowanie kodu

| Właściwość | Opis | Choices |
|--|--|--|
| Umieść kod niezależny | Generuje kod niezależny od pozycji (PIC) do użycia w bibliotece udostępnionej. |
| Elementy statyczne są wątkowo bezpieczne | Emituje dodatkowy kod, aby użyć procedur określonych w języku C++ ABI na potrzeby inicjowania bezpiecznego wątku lokalnych elementów statycznych. | **Nie** — Wyłącz statycznie bezpieczne dla wątków.<br/>**Tak** — Włącz statycznie bezpieczne wątki. |
| Optymalizacja liczb zmiennoprzecinkowych | Włącza optymalizacje zmiennoprzecinkowe przez złagodzeniu wymagań dotyczących zgodności IEEE-754. |
| Ukryte metody wbudowane | Po włączeniu tej metody są deklarowane out-of-Line kopie metod wbudowanych `private extern` . |
| Symbole są domyślnie ukryte | Wszystkie symbole są deklarowane `private extern` , chyba że zostaną jawnie oznaczone do eksportu przy użyciu `__attribute` makra. |
| Włącz wyjątki C++ | Określa model obsługi wyjątków używany przez kompilator. | **Nie** -Wyłącz obsługę wyjątków.<br/>**Tak** — Włącz obsługę wyjątków. |

## <a name="language"></a>Język

| Właściwość | Opis | Choices |
|--|--|--|
| Włącz informacje o typach Run-Time | Dodaje kod do sprawdzania typów obiektów C++ w czasie wykonywania (informacje o typie środowiska uruchomieniowego).     (frtti, FNO-RTTI) |
| Standard języka C | Określa standard języka C. | **Domyślny**<br/>Standard języka **C89** -c89.<br/>Standard języka **C99** -C99.<br/>Standard języka **C11** -C11.<br/>Standard języka **C99 (DIALEKT GNU)** — C99 (dialekt GNU).<br/>Standard języka **C11 (DIALEKT GNU)** — C11 (dialekt GNU). |
| Standard języka C++ | Określa standard języka C++. | **Domyślny**<br/>Standard języka **C++ 03** -c++ 03.<br/>Standard języka **C++ 11** — c++ 11.<br/>Standard języka **C++ 14** -c++ 14.<br/>**C++ 03 (DIALEKT GNU)** — Standard języka c++ 03 (dialekt GNU).<br/>**C++ 11 (DIALEKT GNU)** — Standard języka c++ 11 (dialekt GNU).<br/>**C++ 14 (DIALEKT GNU)** — Standard języka c++ 14 (dialekt GNU). |

## <a name="advanced"></a>Zaawansowane

| Właściwość | Opis | Choices |
|--|--|--|
| Kompiluj jako | Wybiera opcję języka kompilacji dla plików. c i. cpp. (-x c,-x c++) | **Domyślne** — wykrywanie na podstawie rozszerzenia. c lub. cpp.<br/>**Kompiluj jako kod c** Kompiluj jako kod c.<br/>**Kompiluj jako kod języka c++** — Kompiluj jako kod języka c++. |
| Wymuszone pliki dołączane | Określa co najmniej jeden wymuszony plik dyrektywy include (-include \[ name]) |

::: moniker-end
