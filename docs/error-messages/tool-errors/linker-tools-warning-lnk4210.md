---
description: 'Dowiedz się więcej o: LNK4210 ostrzeżenia narzędzi konsolidatora'
title: Ostrzeżenie LNK4210 narzędzi konsolidatora
ms.date: 11/04/2016
f1_keywords:
- LNK4210
helpviewer_keywords:
- LNK4210
ms.assetid: db48cff8-a2be-4a77-8d03-552b42c228fa
ms.openlocfilehash: 7634952df026dc664aed2a2f9625a7380b3a38b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150608"
---
# <a name="linker-tools-warning-lnk4210"></a>Ostrzeżenie LNK4210 narzędzi konsolidatora

> Sekcja *sekcji istnieje;* mogą występować nieobsłużone statyczne inicjatory lub terminatory

## <a name="remarks"></a>Uwagi

Jakiś kod wprowadził statyczne inicjatory lub terminatory, ale kod uruchomienia biblioteki VCRuntime lub jego odpowiednik (który wymaga uruchomienia inicjatorów statycznych lub terminatorów) nie jest uruchamiany podczas uruchamiania aplikacji. Poniżej przedstawiono kilka przykładów kodu, które wymagają statycznych inicjatorów lub terminatorów:

- Globalna zmienna klasy z konstruktorem, destruktorem lub tabelą funkcji wirtualnych.

- Zmienna globalna została zainicjowana z użyciem stałej czasowej innej niż kompilacja.

Aby rozwiązać ten problem, wypróbuj jedną z następujących czynności:

- Usuń cały kod z inicjatorami statycznymi.

- Nie należy używać [/NOENTRY](../../build/reference/noentry-no-entry-point.md). Po usunięciu/NOENTRY może być również konieczne usunięcie [/NODEFAULTLIB](../../build/reference/nodefaultlib-ignore-libraries.md) z wiersza polecenia konsolidatora.

- Jeśli kompilacja używa/MT, Dodaj libcmt. lib, libvcruntime. lib i libucrt. lib do wiersza polecenia konsolidatora. Jeśli kompilacja używa/MTd, Dodaj libcmtd. lib, vcruntimed. lib i libucrtd. lib.

- Podczas przechodzenia z opcji/CLR: Pure kompilację do/CLR Usuń opcję [/entry](../../build/reference/entry-entry-point-symbol.md) z linii konsolidatora. Umożliwia to inicjowanie CRT i zezwala na wykonywanie statycznych inicjatorów podczas uruchamiania aplikacji. **/CLR: Pure** kompilator Option jest przestarzały w programie visual Studio 2015 i nieobsługiwany w programie visual Studio 2017.

Opcja kompilatora [/GS](../../build/reference/gs-buffer-security-check.md) wymaga inicjalizacji przez `__security_init_cookie` funkcję. Ta Inicjalizacja jest domyślnie dostępna w kodzie uruchomieniowym biblioteki VCRuntime, który działa w programie `_DllMainCRTStartup` .

- Jeśli projekt został skompilowany przy użyciu/ENTRY i jeśli/ENTRY jest przenoszona funkcja inna niż `_DllMainCRTStartup` , funkcja musi wywołać, `_CRT_INIT` Aby zainicjować CRT. To wywołanie nie jest wystarczające, jeśli biblioteka DLL używa/GS, wymaga inicjatorów statycznych lub jest wywoływana w kontekście kodu MFC lub ATL. Aby uzyskać więcej informacji [, zobacz biblioteki DLL i zachowanie biblioteki czasu wykonywania Visual C++](../../build/run-time-library-behavior.md) .

## <a name="see-also"></a>Zobacz też

- [Ustawianie opcji konsolidatora](../../build/reference/linking.md)
