---
description: 'Dowiedz się więcej o usłudze: przekazywanie dalej (C++/CLI)'
title: Przekazywanie dalej typu (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- type forwarding, C++
ms.assetid: ae730b69-0c27-41cc-84e1-3132783866ea
ms.openlocfilehash: 360ca624103c8021c17300f897b1091c13e898a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97172885"
---
# <a name="type-forwarding-ccli"></a>Przekazywanie dalej typu (C++/CLI)

*Przekazywanie typu* umożliwia przeniesienie typu z jednego zestawu (zestawu a) do innego zestawu (zestawu B), tak aby nie trzeba było ponownie kompilować klientów korzystających z zestawu a.

## <a name="windows-runtime"></a>Środowisko wykonawcze systemu Windows

Ta funkcja nie jest obsługiwana w środowisko wykonawcze systemu Windows.

## <a name="common-language-runtime"></a>środowiska uruchomieniowe w trakcie wykonania

Poniższy przykład kodu demonstruje, jak używać przekazywania typu.

### <a name="syntax"></a>Składnia

```cpp
#using "new.dll"
[assembly:TypeForwardedTo(type::typeid)];
```

### <a name="parameters"></a>Parametry

*Nowy*<br/>
Zestaw, do którego jest przenoszona definicja typu.

*Wprowadź*<br/>
Typ, którego definicja jest przenoszona do innego zestawu.

### <a name="remarks"></a>Uwagi

Gdy składnik (zestaw) jest używany przez aplikacje klienckie, można użyć przesyłania dalej typu w celu przeniesienia typu z składnika (zestawu) do innego zestawu, wysłania zaktualizowanego składnika (oraz wszelkich dodatkowych zestawów wymaganych), a aplikacje klienckie nadal będą działały bez ponownego kompilowania.

Przekazywanie typu działa tylko dla składników, do których odwołują się istniejące aplikacje. Podczas odbudowywania aplikacji muszą istnieć odpowiednie odwołania do zestawów dla wszystkich typów używanych w aplikacji.

Podczas przekazywania typu (typu A) z zestawu, należy dodać `TypeForwardedTo` atrybut dla tego typu, a także odwołanie do zestawu. Zestaw, do którego się odwołuje, musi zawierać jedną z następujących czynności:

- Definicja typu A.

- `TypeForwardedTo`Atrybut typu A, a także odwołanie do zestawu.

Przykłady typów, które mogą być przekazywane, obejmują:

- klasy referencyjne

- klasy wartości

- typy wyliczeniowe

- interfejsy

Nie można przekazywać następujących typów:

- Typy ogólne

- Typy natywne

- Zagnieżdżone typy (Jeśli chcesz przekazywać Typ zagnieżdżony, należy przekazać typ otaczający)

Można przesłać dalej typ do zestawu, który został utworzony w dowolnym języku przeznaczonym dla środowiska uruchomieniowego języka wspólnego.

Dlatego jeśli plik kodu źródłowego, który jest używany do kompilowania A.dll zestawu zawiera definicję typu ( `ref class MyClass` ) i chcesz przenieść definicję tego typu do B.dll zestawu, można:

1. Przenieś `MyClass` definicję typu do pliku kodu źródłowego służącego do kompilowania B.dll.

2. Kompiluj B.dll zestawu

3. Usuń `MyClass` definicję typu z kodu źródłowego użytego do skompilowania A.dll i zastąp go następującym:

    ```cpp
    #using "B.dll"
    [assembly:TypeForwardedTo(MyClass::typeid)];
    ```

4. Kompiluj A.dll zestawu.

5. Użyj A.dll bez ponownego kompilowania aplikacji klienckich.

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/clr`
