---
description: 'Dowiedz się więcej na temat: błąd krytyczny C1001'
title: Błąd krytyczny C1001
ms.date: 11/04/2016
f1_keywords:
- C1001
helpviewer_keywords:
- C1001
ms.assetid: 5736cdb3-22c8-4fad-aa85-d5e0d2b232f4
ms.openlocfilehash: a00e8bc2fe79201f77f67eac6f0756e90eba462b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262831"
---
# <a name="fatal-error-c1001"></a>Błąd krytyczny C1001

> WEWNĘTRZNY błąd kompilatora ( *plik* pliku kompilatora, *numer* wiersza)

Kompilator nie może wygenerować poprawnego kodu dla konstrukcji, często z powodu kombinacji określonego wyrażenia i opcji optymalizacji lub problemu podczas analizowania. Jeśli wymieniony plik kompilatora ma segment ścieżki UTC lub C2, prawdopodobnie jest to błąd optymalizacji. Jeśli plik zawiera segment ścieżki cxxfe lub c1xx lub jest MSC1. cpp, prawdopodobnie wystąpił błąd parsera. Jeśli plik o nazwie jest cl.exe, żadne inne informacje nie są dostępne.

Problem optymalizacji można często rozwiązać, usuwając co najmniej jedną opcję optymalizacji. Aby określić, która opcja jest uszkodzona, usuń opcje pojedynczo i ponownie skompiluj do momentu, gdy komunikat o błędzie nie zniknie. Opcje najczęściej odpowiedzialne są [/og (optymalizacje globalne)](../../build/reference/og-global-optimizations.md) i [/Oi (Generuj funkcje wewnętrzne)](../../build/reference/oi-generate-intrinsic-functions.md). Po określeniu, która opcja optymalizacji jest odpowiedzialna, można wyłączyć ją wokół funkcji, w której występuje błąd przy użyciu [optymalizacji](../../preprocessor/optimize.md) dyrektywy pragma i nadal używać opcji dla reszty modułu. Aby uzyskać więcej informacji na temat opcji optymalizacji, zobacz [najlepsze rozwiązania dotyczące optymalizacji](../../build/optimization-best-practices.md).

Jeśli optymalizacje nie odpowiadają za błąd, spróbuj ponownie napisać wiersz, w którym jest raportowany błąd, lub kilka wierszy kodu otaczających ten wiersz. Aby wyświetlić kod, w jaki kompilator widzi po wstępnej przetworzenia, możesz użyć opcji [/p (wstępnie przetwórz plik do pliku)](../../build/reference/p-preprocess-to-a-file.md) .

Aby uzyskać więcej informacji na temat sposobu izolowania źródła błędu i sposobu zgłaszania wewnętrznego błędu kompilatora firmie Microsoft, zobacz artykuł [Jak zgłosić problem z zestawem narzędzi Visual C++](../../overview/how-to-report-a-problem-with-the-visual-cpp-toolset.md).
