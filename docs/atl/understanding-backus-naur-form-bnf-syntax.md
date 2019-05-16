---
title: Rejestrator ALT i notacji Backusa-Naura składni formularza (BNF)
ms.date: 05/14/2019
helpviewer_keywords:
- BNF notation
- Backus-Naur form (BNF) syntax
ms.assetid: 994bbef0-9077-4aa8-bdfe-b7e830af9acc
ms.openlocfilehash: 77f0fa6fef8e517e5714d1da6c61d0e310e0718c
ms.sourcegitcommit: fc1de63a39f7fcbfe2234e3f372b5e1c6a286087
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 05/15/2019
ms.locfileid: "65709161"
---
# <a name="understanding-backus-naur-form-bnf-syntax"></a>Opis składni formularza (BNF) notacji Backusa-Naura

Skrypty używane przez rejestrator ALT są opisane w tym temacie, przy użyciu składni BNF, który używa notacji pokazano w poniższej tabeli.

|Konwencja/symbol|Znaczenie|
|------------------------|-------------|
|::=|Odpowiednik|
|&#124;|LUB|
|X+|Co najmniej jeden Xs.|
|\[X]|X jest opcjonalne. Ograniczniki opcjonalne są wskazywane przez \[].|
|Wszelkie **bold** tekstu|Literał ciągu.|
|Wszelkie *kursywą* tekstu|Jak utworzyć literału ciągu.|

Jak wskazano w powyższej tabeli, skrypty rejestratora Używaj literałów ciągów. Te wartości są rzeczywiste tekst, który musi znajdować się w skrypcie. W poniższej tabeli opisano literałów ciągów używanych w skrypcie Rejestrator ALT.

|Literał ciągu|Akcja|
|--------------------|------------|
|**ForceRemove**|Powoduje całkowite usunięcie kluczowi (jeśli istnieje), a następnie ponownie tworzy go.|
|**NoRemove**|Nie powoduje usunięcia kluczowi podczas wyrejestrowania.|
|**Val**|Określa, że `<Key Name>` jest faktycznie nazwanej wartości.|
|**Delete**|Usuwa następny klucz w rejestrze.|
|**s**|Określa następną wartość ciągu (REG_SZ).|
|**d**|Określa następną wartość DWORD (REG_DWORD).|
|**m**|Określa, że wartość następnego FixedLength (REG_MULTI_SZ).|
|**b**|Określa, że następną wartość jest wartością binarną (REG_BINARY).|

## <a name="bnf-syntax-examples"></a>Przykłady składni BNF

Poniżej przedstawiono kilka przykładów składni, aby pomóc Ci zrozumieć, jak i notacji literałów współdziałać w skrypcie Rejestrator ALT.

### <a name="syntax-example-1"></a>Przykład składni 1

```
<registry expression> ::= <Add Key>
```

Określa, że `registry expression` jest odpowiednikiem `Add Key`.

### <a name="syntax-example-2"></a>Przykład składni 2

```
<registry expression> ::= <Add Key> | <Delete Key>
```

Określa, że `registry expression` jest równoważny z typem `Add Key` lub `Delete Key`.

### <a name="syntax-example-3"></a>Przykład składni 3

```
<Key Name> ::= '<AlphaNumeric>+'
```

Określa, że `Key Name` jest odpowiednikiem co najmniej jeden `AlphaNumerics`.

### <a name="syntax-example-4"></a>Przykład składni 4

```
<Add Key> ::= [ForceRemove | NoRemove | val]<Key Name>
```

Określa, że `Add Key` jest odpowiednikiem `Key Name`oraz że literały ciągów `ForceRemove`, `NoRemove`, i `val`, są opcjonalne.

### <a name="syntax-example-5"></a>Przykład składni 5

```
<AlphaNumeric> ::= any character not NULL, that is, ASCII 0
```

Określa, że `AlphaNumeric` jest równoważna do dowolnego znak NIEPUSTY.

### <a name="syntax-example-6"></a>Przykład składni 6

```
val 'testmulti' = m 'String 1\0String 2\0'
```

Określa, że nazwa klucza `testmulti` wartości wielociągu składa się z `String 1` i `String 2`.

### <a name="syntax-example-7"></a>Przykład składni 7

```
val 'testhex' = d '&H55'
```

Określa, że nazwa klucza `testhex` ustawiono wartość DWORD na szesnastkowe 55 (dziesiętna 85). Ten format jest zgodna Uwaga **& H** notacji, jak znaleźć w specyfikacji języka Visual Basic.

## <a name="see-also"></a>Zobacz także

[Tworzenie skryptów rejestratora](../atl/creating-registrar-scripts.md)