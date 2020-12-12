---
description: Dowiedz się więcej na temat:/SAFESEH (obraz ma bezpieczne procedury obsługi wyjątków)
title: /SAFESEH (Obraz ma bezpieczną obsługę wyjątków)
ms.date: 11/04/2016
f1_keywords:
- /SAFESEH
helpviewer_keywords:
- /SAFESEH linker option
- -SAFESEH linker option
- SAFESEH linker option
ms.assetid: 7722ff99-b833-4c65-a855-aaca902ffcb7
ms.openlocfilehash: 723b5503bca1d98d7df0c638df1dfc8101fc116f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224988"
---
# <a name="safeseh-image-has-safe-exception-handlers"></a>/SAFESEH (Obraz ma bezpieczną obsługę wyjątków)

```
/SAFESEH[:NO]
```

Gdy **/SAFESEH** jest określony, konsolidator będzie generować tylko obraz, jeśli może również generować tabelę obsługi wyjątków bezpiecznego obrazu. Ta tabela określa dla systemu operacyjnego, które programy obsługi wyjątków są prawidłowe dla obrazu.

**/SAFESEH** jest prawidłowy tylko podczas łączenia z obiektami docelowymi x86. **/SAFESEH** nie jest obsługiwana dla platform, które mają już zanotowane programy obsługi wyjątków. Na przykład w przypadku architektury x64 i ARM wszystkie programy obsługi wyjątków są notowane w PDATA. ML64.exe obsługuje dodawanie adnotacji, które emitują informację strukturalnej obsługi wyjątków (XDATA i PDATA) do obrazu, pozwalając na odpoczynek, dzięki funkcji ml64. Aby uzyskać więcej informacji, zobacz [MASM for x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md) .

Jeśli **/SAFESEH** nie zostanie określony, konsolidator utworzy obraz z tabelą obsługi bezpiecznych wyjątków, jeśli wszystkie moduły są zgodne z funkcją obsługi wyjątków bezpiecznych. Jeśli wszystkie moduły nie były zgodne z funkcją obsługi bezpiecznych wyjątków, obraz wynikowy nie będzie zawierać tabeli obsługi bezpiecznych wyjątków. Jeśli [/Subsystem](subsystem-specify-subsystem.md) określa WindowsCE lub jedną z opcji EFI_ * konsolidator nie podejmie próby utworzenia obrazu z tabelą obsługi bezpiecznych wyjątków, ponieważ żaden z tych podsystemów nie będzie mógł korzystać z informacji.

Jeśli **/SAFESEH: nie** jest określona, konsolidator nie będzie generował obrazu z tabelą obsługi bezpiecznych wyjątków, nawet jeśli wszystkie moduły są zgodne z funkcją obsługi wyjątków bezpiecznych.

Najczęstszą przyczyną, dla której konsolidator nie może wyprodukować obrazu, jest brak zgodności z funkcją obsługi bezpiecznych wyjątków z konsolidatorem, przez jeden lub więcej plików wejściowych (modułów). Częstą przyczyną niezgodności modułu z obsługą bezpiecznych wyjątków jest utworzenie modułu przy użyciu kompilatora poprzednich wersji programu Visual C++.

Funkcję można także zarejestrować jako procedurę obsługi wyjątków strukturalnych za pomocą programu [. SAFESEH](../../assembler/masm/dot-safeseh.md).

Nie istnieje możliwość oznaczenia istniejących danych binarnych jako posiadające obsługę wyjątków bezpiecznych (lub brak obsługi wyjątków); informację na temat obsługi wyjątków bezpiecznych muszą zostać dodane w czasie kompilacji.

Konsolidator posiada możliwość utworzenia tabeli obsługi bezpiecznych wyjątków zależnych od aplikacji przy użyciu biblioteki środowiska uruchomieniowego C. Jeśli połączysz się z [/NODEFAULTLIB](nodefaultlib-ignore-libraries.md) i potrzebujesz tabeli obsługi bezpiecznych wyjątków, musisz podać strukturę konfiguracji ładowania (taką jak można znaleźć w pliku źródłowym CRT LoadCfg. c), który zawiera wszystkie wpisy zdefiniowane dla Visual C++. Na przykład:

```
#include <windows.h>
extern DWORD_PTR __security_cookie;  /* /GS security cookie */

/*
* The following two names are automatically created by the linker for any
* image that has the safe exception table present.
*/

extern PVOID __safe_se_handler_table[]; /* base of safe handler entry table */
extern BYTE  __safe_se_handler_count;  /* absolute symbol whose address is
                                           the count of table entries */
typedef struct {
    DWORD       Size;
    DWORD       TimeDateStamp;
    WORD        MajorVersion;
    WORD        MinorVersion;
    DWORD       GlobalFlagsClear;
    DWORD       GlobalFlagsSet;
    DWORD       CriticalSectionDefaultTimeout;
    DWORD       DeCommitFreeBlockThreshold;
    DWORD       DeCommitTotalFreeThreshold;
    DWORD       LockPrefixTable;            // VA
    DWORD       MaximumAllocationSize;
    DWORD       VirtualMemoryThreshold;
    DWORD       ProcessHeapFlags;
    DWORD       ProcessAffinityMask;
    WORD        CSDVersion;
    WORD        Reserved1;
    DWORD       EditList;                   // VA
    DWORD_PTR   *SecurityCookie;
    PVOID       *SEHandlerTable;
    DWORD       SEHandlerCount;
} IMAGE_LOAD_CONFIG_DIRECTORY32_2;

const IMAGE_LOAD_CONFIG_DIRECTORY32_2 _load_config_used = {
    sizeof(IMAGE_LOAD_CONFIG_DIRECTORY32_2),
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    0,
    &__security_cookie,
    __safe_se_handler_table,
    (DWORD)(DWORD_PTR) &__safe_se_handler_count
};
```

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>Aby ustawić tę opcję konsolidatora w środowisku programowania Visual Studio

1. Otwórz okno dialogowe **strony właściwości** projektu. Aby uzyskać szczegółowe informacje, zobacz [Ustawianie kompilatora C++ i właściwości kompilacji w programie Visual Studio](../working-with-project-properties.md).

1. Wybierz folder **konsolidatora** .

1. Wybierz stronę właściwości **wiersza polecenia** .

1. Wprowadź opcję w polu **dodatkowe opcje** .

### <a name="to-set-this-linker-option-programmatically"></a>Aby programowo ustawić tę opcję konsolidatora

- Zobacz: <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>.

## <a name="see-also"></a>Zobacz też

[Dokumentacja konsolidatora MSVC](linking.md)<br/>
[MSVC Opcje konsolidatora](linker-options.md)
