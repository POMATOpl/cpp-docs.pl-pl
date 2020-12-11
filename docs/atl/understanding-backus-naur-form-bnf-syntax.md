---
description: 'Dowiedz się więcej o: zrozumienie składni formularza Backus-Naur (BNF)'
title: Składnia rejestratora ATL i formularz Backus-Naur (BNF)
ms.date: 05/14/2019
helpviewer_keywords:
- BNF notation
- Backus-Naur form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
ms.openlocfilehash: 7f392d442c4d43865faf9e788f8bf69288673398
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157350"
---
# <a name="understanding-backus-naur-form-bnf-syntax"></a>Opis składni notacji Backusa-Naura (BNF)

Skrypty używane przez rejestrator ATL są opisane w tym temacie przy użyciu składni BNF, która korzysta z notacji pokazanej w poniższej tabeli.

|Konwencja/symbol|Znaczenie|
|------------------------|-------------|
|::=|Odpowiednik|
|&#124;|LUB|
|X +|Jeden lub więcej XS.|
|\[Y|Symbol X jest opcjonalny. Opcjonalne ograniczniki są oznaczane przez \[ ].|
|Dowolny **pogrubiony** tekst|Literał ciągu.|
|Dowolny tekst *pisany kursywą*|Sposób konstruowania literału ciągu.|

Jak wskazano w powyższej tabeli, skrypty rejestratora używają literałów ciągów. Te wartości są rzeczywistym tekstem, który musi pojawić się w skrypcie. W poniższej tabeli opisano literały ciągów używane w skrypcie rejestratora ATL.

|Literał ciągu|Akcja|
|--------------------|------------|
|**ForceRemove**|Całkowicie usuwa następny klucz (jeśli istnieje), a następnie ponownie go tworzy.|
|**NoRemove**|Nie usuwa następnego klucza podczas wyrejestrowywania.|
|**użyte**|Określa, że `<Key Name>` jest to nazwana wartość.|
|**Usuwanie**|Usuwa następny klucz podczas rejestrowania.|
|**s**|Określa, że następna wartość jest ciągiem (REG_SZ).|
|**d**|Określa, że następna wartość jest typu DWORD (REG_DWORD).|
|**m**|Określa, że następna wartość jest wielociągu (REG_MULTI_SZ).|
|**b**|Określa, że następna wartość jest wartością binarną (REG_BINARY).|

## <a name="bnf-syntax-examples"></a>Przykłady składni BNF

Poniżej przedstawiono kilka przykładów składni, które ułatwią zrozumienie, jak Notacja i literały ciągu działają w skrypcie rejestratora ATL.

### <a name="syntax-example-1"></a>Przykład składni 1

> \<registry expression> ::= \<Add Key>

Określa, że `registry expression` jest równoważne `Add Key` .

### <a name="syntax-example-2"></a>Przykład składni 2

> \<registry expression> ::= \<Add Key> | \<Delete Key>

Określa, że `registry expression` jest równoważne albo `Add Key` lub `Delete Key` .

### <a name="syntax-example-3"></a>Przykład składni 3

> \<Key Name> ::= '\<AlphaNumeric>+'

Określa, że `Key Name` jest równa co najmniej jednej `AlphaNumeric` wartości.

### <a name="syntax-example-4"></a>Przykład składni 4

> \<Add Key>:: = [**ForceRemove**  |  **NoRemove**  |  **Val**]\<Key Name>

Określa, że `Add Key` jest równoważne z `Key Name` , i że literały ciągu, `ForceRemove` , `NoRemove` , i `val` , są opcjonalne.

### <a name="syntax-example-5"></a>Przykład składni 5

> \<AlphaNumeric> :: = *dowolny znak, który nie ma wartości null, czyli ASCII 0*

Określa, że `AlphaNumeric` jest równoznaczny z dowolnym znakiem innym niż null.

### <a name="syntax-example-6"></a>Przykład składni 6

```rgs
val 'testmulti' = m 'String 1\0String 2\0'
```

Określa, że nazwa klucza `testmulti` jest wartością wielociągową składającą się z `String 1` i `String 2` .

### <a name="syntax-example-7"></a>Przykład składni 7

```rgs
val 'testhex' = d '&H55'
```

Określa, że nazwa klucza `testhex` jest wartością DWORD ustawioną na szesnastkowe 55 (dziesiętne 85). Należy pamiętać, że ten format jest zgodny z notacją **&H** , jak znaleziono w specyfikacji Visual Basic.

## <a name="see-also"></a>Zobacz też

[Tworzenie skryptów rejestratora](../atl/creating-registrar-scripts.md)
