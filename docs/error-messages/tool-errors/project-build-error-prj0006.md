---
description: 'Dowiedz się więcej na temat: błąd kompilacji projektu PRJ0006'
title: Błąd PRJ0006 kompilacji projektu
ms.date: 11/04/2016
f1_keywords:
- PRJ0006
helpviewer_keywords:
- PRJ0006
ms.assetid: ce092be4-1652-414f-8cb5-b97ef5841f89
ms.openlocfilehash: a78646c843a6c6df3b4e2847076670492a9efb6b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97343928"
---
# <a name="project-build-error-prj0006"></a>Błąd PRJ0006 kompilacji projektu

Nie można otworzyć pliku tymczasowego "File". Upewnij się, że plik istnieje i że katalog nie jest chroniony przed zapisem.

Visual C++ nie mógł utworzyć pliku tymczasowego podczas procesu kompilacji. Przyczyny tego zastosowania:

- Brak katalogu tymczasowego.

- Katalog tymczasowy tylko do odczytu.

- Brak miejsca na dysku.

- Folder $ (IntDir) jest w trybie tylko do odczytu lub zawiera pliki tymczasowe, które są tylko do odczytu.

Ten błąd wystąpi również po wystąpieniu błędu PRJ0007: nie można utworzyć katalogu wyjściowego "Directory". Błąd PRJ0007 oznacza, że nie można utworzyć katalogu $ (IntDir), co oznacza, że tworzenie tymczasowego plików również zakończy się niepowodzeniem.

Pliki tymczasowe są tworzone po każdym określeniu:

- Plik odpowiedzi.

- Niestandardowy krok kompilacji.

- Zdarzenie kompilacji.
