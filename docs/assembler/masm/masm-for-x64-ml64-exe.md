---
description: 'Dowiedz się więcej na temat: MASM for x64 (ml64.exe)'
title: MASM dla wersji x64 (ml64.exe)
ms.date: 12/17/2019
helpviewer_keywords:
- ml64
- ml64.exe
- masm for x64
ms.assetid: 89059103-f372-4968-80ea-0c7f90bb9c91
ms.openlocfilehash: 58970f65fbd98b4cbebae0a36c615cb380ec5b75
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129730"
---
# <a name="masm-for-x64-ml64exe"></a>MASM dla wersji x64 (ml64.exe)

Program Visual Studio zawiera zarówno 32-bitowe, jak i 64-bitowe obsługiwane wersje asemblera firmy Microsoft (MASM), aby obsługiwały kod x64. Nazwana ml64.exe, to jest asembler, który akceptuje język asemblera x64. Narzędzia wiersza polecenia MASM są instalowane w przypadku wybrania obciążenia C++ podczas instalacji programu Visual Studio. Narzędzia MASM nie są dostępne w oddzielnym pobieraniu. Aby uzyskać instrukcje dotyczące pobierania i instalowania kopii programu Visual Studio, zobacz [Instalowanie programu Visual Studio](/visualstudio/install/install-visual-studio). Jeśli nie chcesz instalować kompletnego środowiska IDE programu Visual Studio, ale potrzebujesz tylko narzędzi wiersza polecenia, Pobierz [narzędzia kompilacji dla programu Visual Studio](https://visualstudio.microsoft.com/downloads/#build-tools-for-visual-studio-2019).

Aby użyć MASM do kompilowania kodu dla obiektów docelowych x64 w wierszu polecenia, należy użyć wiersza polecenia dewelopera dla obiektów docelowych x64, które ustawia wymaganą ścieżkę i inne zmienne środowiskowe. Aby uzyskać informacje na temat sposobu uruchamiania wiersza polecenia dewelopera, zobacz [kompilowanie kodu C/C++ w wierszu polecenia](../../build/building-on-the-command-line.md).

Aby uzyskać informacje o ml64.exe opcjach wiersza polecenia, zobacz artykuł [ml i ML64 Command-Line Reference](ml-and-ml64-command-line-reference.md).

Wbudowane asembler lub użycie słowa kluczowego ASM nie jest obsługiwane dla elementów docelowych x64 i ARM. Aby przenieść kod x86, który używa asemblera wbudowanego do architektury x64 lub ARM, Możesz skonwertować kod na język C++, użyć funkcji wewnętrznych kompilatora lub utworzyć pliki źródłowe języka asemblera. Kompilator języka Microsoft C++ obsługuje funkcje wewnętrzne, aby umożliwić korzystanie z instrukcji specjalnych, na przykład uprzywilejowanych, w przypadku skanowania bitowego/testowania, zablokowania i tak dalej, w przypadku, gdy jest to możliwe. Aby uzyskać informacje o dostępnych funkcjach wewnętrznych, zobacz [wewnętrzne kompilatory](../../intrinsics/compiler-intrinsics.md).

## <a name="add-an-assembler-language-file-to-a-visual-studio-c-project"></a>Dodawanie pliku z językiem asemblera do projektu Visual Studio C++

System projektu programu Visual Studio obsługuje pliki języka asemblera skompilowane przy użyciu MASM w projektach języka C++. Można tworzyć pliki źródłowe języka asemblera x64 i kompilować je w plikach obiektów przy użyciu MASM, który obsługuje 64 w pełni. Następnie można połączyć te pliki obiektów z kodem C++ skompilowanym dla celów x64. Jest to jeden ze sposobów na przezwyciężenie braku wbudowanego asemblera x64.

### <a name="to-add-an-assembler-language-file-to-an-existing-visual-studio-c-project"></a>Aby dodać plik programu asemblera do istniejącego projektu Visual Studio C++

1. Wybierz projekt w **Eksplorator rozwiązań**. Na pasku menu wybierz **projekt**, a następnie pozycję **dostosowania kompilacji**.

1. W oknie dialogowym **Visual C++ pliki dostosowania kompilacji** zaznacz pole wyboru obok pozycji **MASM (. targets,. props)**. Wybierz **przycisk OK** , aby zapisać wybór i zamknąć okno dialogowe.

1. Na pasku menu wybierz **projekt**, **Dodaj nowy element**.

1. W oknie dialogowym **Dodaj nowy element** wybierz opcję **plik C++ (. cpp)** w środkowym okienku. W kontrolce Edycja **nazwy** wprowadź nową nazwę pliku o rozszerzeniu **. asm** zamiast. cpp. Wybierz pozycję **Dodaj** , aby dodać plik do projektu i zamknąć okno dialogowe.

Utwórz kod języka asemblera w pliku. ASM, który został dodany. Podczas kompilowania rozwiązania MASM asembler jest wywoływany, aby złożyć plik. asm do pliku obiektu, który jest następnie połączony z projektem. Aby ułatwić dostęp do symboli, należy zadeklarować asembler w taki sposób jak `extern "C"` w kodzie źródłowym języka c++, a nie przy użyciu konwencji dekoracji nazw c++ w plikach źródłowych języka asemblera.

## <a name="ml64-specific-directives"></a>Dyrektywy specyficzne dla ml64

W kodzie źródłowym języka asemblera, który jest przeznaczony dla architektury x64, można użyć następujących dyrektyw specyficznych dla ML64:

- [.ALLOCSTACK](dot-allocstack.md)

- [.ENDPROLOG](dot-endprolog.md)

- [.PUSHFRAME](dot-pushframe.md)

- [.PUSHREG](dot-pushreg.md)

- [.SAVEREG](dot-savereg.md)

- [.SAVEXMM128](dot-savexmm128.md)

- [.SETFRAME](dot-setframe.md)

Ponadto dyrektywa [proc](proc.md) została zaktualizowana do użytku z ml64.exe.

## <a name="32-bit-address-mode-address-size-override"></a>32 — tryb adresu bitowego (przesłonięcie rozmiaru adresu)

MASM emituje przesłonięcie rozmiaru adresu 0x67, jeśli argument operacji pamięci zawiera 32-bitowe rejestry. Na przykład następujące przykłady powodują wydawanie przesłania rozmiaru adresu:

```asm
mov rax, QWORD PTR [ecx]
mov eax, DWORD PTR [ecx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10d+0100h]
prefetch [eax]
movnti rax, QWORD PTR [r8d]
```

MASM zakłada, że jeśli przemieszczenie 32-bitowe występuje pojedynczo jako operand pamięci, adres 64-bitowy jest zamierzony. Obecnie nie są obsługiwane adresy 32-bitowe z takimi operandami.

Na koniec mieszanie rozmiarów rejestru w obrębie operandu pamięci, jak pokazano w poniższym kodzie, generuje błąd.

```asm
mov eax, DWORD PTR [rcx*2+r10d]
mov eax, DWORD PTR [ecx*2+r10+0100h]
```

## <a name="see-also"></a>Zobacz też

[Microsoft Macro Assembler — dokumentacja](microsoft-macro-assembler-reference.md)
