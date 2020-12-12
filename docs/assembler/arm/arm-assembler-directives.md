---
description: 'Dowiedz się więcej na temat: dyrektywy asemblera ARM'
title: Dyrektywy ARM dotycząca asemblera
ms.date: 08/30/2018
ms.assetid: 9cfa8896-ec10-4e77-855a-3135c40d7d2a
ms.openlocfilehash: 8362453f2113922c5e834d1d68583b4199cf8d4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118121"
---
# <a name="arm-assembler-directives"></a>Dyrektywy ARM dotycząca asemblera

W większości przypadków, asembler Microsoft ARM używa języka zestawu ARM, który jest udokumentowany w [przewodniku odniesienia armasm kompilatora ARM](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html). Jednak implementacje firmy Microsoft niektórych dyrektyw zestawu różnią się od dyrektyw zestawu ARM. W tym artykule opisano różnice.

## <a name="microsoft-implementations-of-arm-assembly-directives"></a>Implementacje dyrektyw zestawu ARM firmy Microsoft

- STREF

   Asembler Microsoft ARM obsługuje następujące atrybuty:,,,,,,, `AREA` `ALIGN` `CODE` `CODEALIGN` `DATA` `NOINIT` `READONLY` `READWRITE` `THUMB` , `ARM` .

   Wszystkie z wyjątkiem `THUMB` i `ARM` pracy zgodnie z opisem w [przewodniku referencyjnym armasm kompilatora ARM](http://infocenter.arm.com/help/topic/com.arm.doc.dui0802b/index.html).

   W asemblerze Microsoft ARM, `THUMB` wskazuje, że `CODE` sekcja zawiera kod kciuka i jest wartością domyślną dla `CODE` sekcji.  `ARM` wskazuje, że sekcja zawiera kod ARM.

- ATRYBUT

   Nieobsługiwane.

- 16

   Nieobsługiwane, ponieważ sugeruje rejestrowania dostępu użytkowników miniaturę, której nie zezwala program Microsoft ARM asembler.  `THUMB`Zamiast tego użyj dyrektywy, wraz ze składnią rejestrowania dostępu użytkowników.

- Wspólna

   Specyfikacja wyrównania dla wspólnego regionu nie jest obsługiwana.

- DCDO

   Nieobsługiwane.

- `DN`, `QN`, `SN`

   Specyfikacja typu lub ścieżki w aliasie rejestru nie jest obsługiwana.

- AUTOTEKSTU

   Nieobsługiwane.

- EQU

   Specyfikacja typu dla zdefiniowanego symbolu nie jest obsługiwana.

- `EXPORT` i `GLOBAL`

   Określa eksporty przy użyciu następującej składni:

   > **Eksportuj** | **Global** <em>symboli</em>{**[**<em>Type</em>**]**}

   *symboli* jest symbolem do wyeksportowania.  [*Type*], jeśli jest określony, może być albo `[DATA]` w celu wskazania, że symbol wskazuje na dane lub `[FUNC]` wskazuje, że symbol wskazuje na kod. `GLOBAL` jest synonimem dla `EXPORT` .

- EXPORTAS

   Nieobsługiwane.

- KLATCE

   Nieobsługiwane.

- `FUNCTION` i `PROC`

   Chociaż składnia zestawu obsługuje specyfikację niestandardowej konwencji wywoływania dotyczącej procedur przez wystawienie rejestrów, które są zapisywane jako wywołujące i które są wywoływane, to program asembler Microsoft ARM akceptuje składnię, ale ignoruje listy rejestrów.  Informacje o debugowaniu, które są tworzone przez asemblera, obsługują tylko domyślną konwencję wywoływania.

- `IMPORT` i `EXTERN`

   Określa Importy przy użyciu następującej składni:

   > **Importuj** | **Extern** *symboli*{**, słaby** *alias*{**, Type** *t*}}

   *symboli* to nazwa symbolu, który ma zostać zaimportowany.

   Jeśli `WEAK` *alias* jest określony, oznacza to, że *symboli* jest słabo zewnętrzny. Jeśli żadna definicja dla tego elementu nie zostanie znaleziona w czasie łącza, wówczas wszystkie odwołania do niego zostaną powiązane z *aliasem*.

   Jeśli `TYPE` *t* jest określony, *t* wskazuje, jak konsolidator powinien próbować rozwiązać *symboli*.  Możliwe wartości *t* są następujące:

   |Wartość|Opis|
   |-|-|
   |1|Nie wykonuj wyszukiwania biblioteki *symboli*|
   |2|Przeprowadź wyszukiwanie biblioteki *symboli*|
   |3|*symboli* jest aliasem *aliasu* (ustawienie domyślne)|

   `EXTERN` jest synonimem dla `IMPORT` , z wyjątkiem tego, że *symboli* jest zaimportowany tylko wtedy, gdy istnieją odwołania do niego w bieżącym zestawie.

- MACRO

   Użycie zmiennej do przechowywania kodu warunku makra nie jest obsługiwane. Wartości domyślne parametrów makra nie są obsługiwane.

- NOFP

   Nieobsługiwane.

- `OPT`, `TTL`, `SUBT`

   Nieobsługiwane, ponieważ asembler Microsoft ARM nie produkuje list.

- PRESERVE8

   Nieobsługiwane.

- RELOC

   `RELOC n` może być tylko zgodna z instrukcją lub dyrektywą definicji danych. Nie ma żadnego "anonimowego symbolu", który może zostać przeniesiony.

- WYMAGANE

   Nieobsługiwane.

- REQUIRE8

   Nieobsługiwane.

- THUMBX

   Nieobsługiwane, ponieważ asembler Microsoft ARM nie obsługuje zestawu instrukcji 2EE.

## <a name="see-also"></a>Zobacz też

[Informacje Command-Line asemblera ARM](../../assembler/arm/arm-assembler-command-line-reference.md)<br/>
[Komunikaty diagnostyczne asemblera ARM](../../assembler/arm/arm-assembler-diagnostic-messages.md)<br/>
