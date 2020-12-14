---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1004'
title: Błąd krytyczny C1004
ms.date: 11/04/2016
f1_keywords:
- C1004
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
ms.openlocfilehash: f21978f5ff314a8273dde60428dc89ca0c5767b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262688"
---
# <a name="fatal-error-c1004"></a>Błąd krytyczny C1004

znaleziono nieoczekiwany koniec pliku

Kompilator osiągnął koniec pliku źródłowego bez rozpoznawania konstrukcji. Kod może nie zawierać jednego z następujących elementów:

- Zamykający nawias klamrowy

- Nawias zamykający

- Znacznik zamykającego komentarza (*/)

- Średnik

Aby rozwiązać ten problem, sprawdź następujące kwestie:

- Na domyślnym dysku nie ma wystarczającej ilości miejsca na pliki tymczasowe, które wymagają około dwukrotnie większej ilości miejsca jako pliku źródłowego.

- `#if`Dyrektywa, której wynikiem jest false, nie ma dyrektywy zamykającej `#endif` .

- Plik źródłowy nie kończy się znakiem powrotu karetki i wysuwu wiersza.

Poniższy przykład generuje C1004:

```cpp
// C1004.cpp
#if TEST
int main() {}
// C1004
```

Możliwe rozwiązanie:

```cpp
// C1004b.cpp
#if TEST
#endif

int main() {}
```
