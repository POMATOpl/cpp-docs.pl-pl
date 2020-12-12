---
description: 'Dowiedz się więcej o: zrozumienie SAL'
title: Poznanie SAL
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: a94d6907-55f2-4874-9571-51d52d6edcfd
ms.openlocfilehash: affbca9eb65467b65ee5ba4ed3ae550a6da25ac7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288506"
---
# <a name="understanding-sal"></a>Poznanie SAL

Język adnotacji kodu źródłowego firmy Microsoft (SAL) zawiera zestaw adnotacji, za pomocą których można opisać, w jaki sposób funkcja używa jej parametrów, przyjętych przez niego założeń i gwarantuje, że po zakończeniu. Adnotacje są zdefiniowane w pliku nagłówkowym `<sal.h>` . Program Visual Studio Code Analysis for C++ używa adnotacji SAL do modyfikowania analizy funkcji. Aby uzyskać więcej informacji na temat SAL 2,0 dla opracowywania sterowników systemu Windows, zobacz [Adnotacje sal 2,0 dla sterowników systemu Windows](/windows-hardware/drivers/devtest/sal-2-annotations-for-windows-drivers).

Natywnie, język C i C++ zapewniają tylko ograniczone sposoby, aby deweloperzy mogli stale wyznaczać intencje i niewariancje. Za pomocą adnotacji SAL można opisać funkcje bardziej szczegółowo, aby deweloperzy korzystający z nich mogli lepiej zrozumieć, jak ich używać.

## <a name="what-is-sal-and-why-should-you-use-it"></a>Co to jest SAL i dlaczego warto z niej korzystać?

Po prostu podano niedrogi, aby umożliwić kompilatorowi Sprawdzanie kodu.

### <a name="sal-makes-code-more-valuable"></a>SAL sprawia, że kod jest bardziej cenny

SAL ułatwia zrozumienie projektu kodu, zarówno dla ludzi, jak i dla narzędzi do analizy kodu. Rozważmy ten przykład, który pokazuje funkcję środowiska uruchomieniowego C `memcpy` :

```cpp

void * memcpy(
   void *dest,
   const void *src,
   size_t count
);
```

Czy można sprawdzić, co to jest funkcja? Po zaimplementowaniu lub wywołaniu funkcji należy zachować pewne właściwości, aby zapewnić poprawność programu. Wystarczy, że szukasz deklaracji, takiej jak ta w przykładzie, nie wiesz, co się stało. Bez adnotacji SAL należy polegać na dokumentacji lub komentarzach do kodu. Oto dokumentacja dotycząca `memcpy` treści:

> " `memcpy` kopiuje *liczbę* bajtów z *src* do miejsca *docelowego*; `wmemcpy` kopiuje znaki w *liczbie* szerokie (dwa bajty). Jeśli źródło i miejsce docelowe nakładają się na siebie, zachowanie `memcpy` jest niezdefiniowane. Służy `memmove` do obsługi nakładających się regionów. \
> **Ważne:** Upewnij się, że bufor docelowy ma ten sam rozmiar lub większy niż bufor źródłowy. Aby uzyskać więcej informacji, zobacz Unikanie przepełnień buforu ".

Dokumentacja zawiera kilka bitów informacji, które sugerują, że Twój kod musi zachować pewne właściwości, aby zapewnić poprawność programu:

- `memcpy` Kopiuje `count` bajty z bufora źródłowego do bufora docelowego.

- Bufor docelowy musi być co najmniej tak duży jak bufor źródłowy.

Jednak kompilator nie może odczytać dokumentacji ani komentarzy nieformalnych. Nie wiadomo, że istnieje relacja między dwoma buforami i `count` i nie może efektywnie odgadnąć relacji. SAL może zapewnić większą przejrzystość właściwości i implementacji funkcji, jak pokazano poniżej:

```cpp

void * memcpy(
   _Out_writes_bytes_all_(count) void *dest,
   _In_reads_bytes_(count) const void *src,
   size_t count
);
```

Zwróć uwagę, że te adnotacje przypominają informacje w dokumentacji, ale są bardziej zwięzłe i są zgodne ze wzorcem semantycznym. Po odczytaniu tego kodu można szybko zrozumieć właściwości tej funkcji oraz uniknąć problemów z zabezpieczeniami przepełnienia buforu. Jeszcze lepsze wzorce semantyczne, które zawiera, mogą zwiększyć wydajność i efektywność zautomatyzowanych narzędzi do analizy kodu w wczesnym wykrywaniu potencjalnych usterek. Załóżmy, że ktoś zapisuje tę implementację debugowania `wmemcpy` :

```cpp

wchar_t * wmemcpy(
   _Out_writes_all_(count) wchar_t *dest,
   _In_reads_(count) const wchar_t *src,
   size_t count)
{
   size_t i;
   for (i = 0; i <= count; i++) { // BUG: off-by-one error
      dest[i] = src[i];
   }
   return dest;
}
```

Ta implementacja zawiera typowy błąd poza jedną. Na szczęście kod autora zawiera adnotację rozmiaru buforu SAL — narzędzie do analizy kodu może przechwycić usterkę, analizując samą funkcję.

### <a name="sal-basics"></a>Podstawowe informacje dotyczące SAL

SAL definiuje cztery podstawowe rodzaje parametrów, które są podzielone według wzorca użycia.

|Kategoria|Adnotacja parametru|Opis|
|--------------|--------------------------|-----------------|
|**Wejście do wywołanej funkcji**|`_In_`|Dane są przesyłane do wywołanej funkcji i są traktowane jako tylko do odczytu.|
|**Wejście do wywoływanej funkcji i wyjście do obiektu wywołującego**|`_Inout_`|Użyteczne dane są przesyłane do funkcji i potencjalnie modyfikowane.|
|**Dane wyjściowe do wywołującego**|`_Out_`|Obiekt wywołujący udostępnia tylko miejsce dla wywoływanej funkcji, do której można pisać. Wywoływana funkcja zapisuje dane w tym miejscu.|
|**Dane wyjściowe wskaźnika do obiektu wywołującego**|`_Outptr_`|**Na przykład dane wyjściowe do obiektu wywołującego**. Wartość zwracana przez wywołaną funkcję jest wskaźnikiem.|

Te cztery podstawowe adnotacje mogą być bardziej jawne na różne sposoby. Domyślnie parametry wskaźnika z adnotacjami są uznawane za wymagane — muszą one mieć wartość różną od NULL, aby funkcja zakończyła się pomyślnie. Najczęściej używana odmiana podstawowych adnotacji wskazuje, że parametr wskaźnika jest opcjonalny — Jeśli ma wartość NULL, funkcja może nadal się powieść w trakcie pracy.

W tej tabeli pokazano, jak rozróżnić parametry wymagane i opcjonalne:

||Parametry są wymagane|Parametry są opcjonalne|
|-|-----------------------------|-----------------------------|
|**Wejście do wywołanej funkcji**|`_In_`|`_In_opt_`|
|**Wejście do wywoływanej funkcji i wyjście do obiektu wywołującego**|`_Inout_`|`_Inout_opt_`|
|**Dane wyjściowe do wywołującego**|`_Out_`|`_Out_opt_`|
|**Dane wyjściowe wskaźnika do obiektu wywołującego**|`_Outptr_`|`_Outptr_opt_`|

Te adnotacje pomagają zidentyfikować możliwe niezainicjowane wartości i nieprawidłowe użycie wskaźnika o wartości null w formalnym i dokładnym sposobie. Przekazywanie wartości NULL do wymaganego parametru może spowodować awarię lub może spowodować zwrócenie kodu błędu "Niepowodzenie". W obu przypadkach funkcja nie może pomyślnie wykonać zadania.

## <a name="sal-examples"></a>Przykłady SAL

W tej sekcji przedstawiono przykłady kodu dla podstawowych adnotacji SAL.

### <a name="using-the-visual-studio-code-analysis-tool-to-find-defects"></a>Korzystanie z narzędzia do analizy Visual Studio Code, aby znaleźć wady

W przykładach narzędzie do analizy Visual Studio Code jest używane razem z adnotacjami SAL do znajdowania wad kodu. Oto jak to zrobić.

#### <a name="to-use-visual-studio-code-analysis-tools-and-sal"></a>Aby korzystać z narzędzi analitycznych i SAL programu Visual Studio Code

1. W programie Visual Studio Otwórz projekt C++ zawierający adnotacje SAL.

1. Na pasku menu wybierz **kompilacja**, **Uruchom analizę kodu w rozwiązaniu**.

     Rozważmy \_ w \_ przykładzie w tej sekcji. Jeśli uruchomisz analizę kodu, to ostrzeżenie jest wyświetlane:

    > **C6387 nieprawidłowa wartość parametru** "Pinta" może mieć wartość "0": to nie jest zgodne ze specyfikacją funkcji "InCallee".

### <a name="example-the-_in_-annotation"></a>Przykład: \_ w \_ adnotacji

`_In_`Adnotacja wskazuje, że:

- Parametr musi być prawidłowy i nie zostanie zmodyfikowany.

- Funkcja zostanie odczytana tylko z bufora jednego elementu.

- Obiekt wywołujący musi dostarczyć bufor i zainicjować go.

- `_In_` Określa wartość "tylko do odczytu". Typowy błąd ma zastosowanie `_In_` do parametru, który powinien mieć `_Inout_` adnotację.

- `_In_` jest dozwolony, ale ignorowany przez analizator dla skalarnych wartości niebędących wskaźnikami.

```cpp
void InCallee(_In_ int *pInt)
{
   int i = *pInt;
}

void GoodInCaller()
{
   int *pInt = new int;
   *pInt = 5;

   InCallee(pInt);
   delete pInt;
}

void BadInCaller()
{
   int *pInt = NULL;
   InCallee(pInt); // pInt should not be NULL
}
```

Jeśli w tym przykładzie używasz analizy Visual Studio Code, sprawdza ona, czy wywołujący przekażą wskaźnik o wartości innej niż null do zainicjowanego buforu dla elementu `pInt` . W tym przypadku `pInt` wskaźnik nie może mieć wartości null.

### <a name="example-the-_in_opt_-annotation"></a>Przykład: \_ w \_ \_ adnotacji opt

`_In_opt_` jest taka sama jak `_In_` , z tą różnicą, że parametr wejściowy może mieć wartość null i dlatego funkcja powinna ją sprawdzić.

```cpp

void GoodInOptCallee(_In_opt_ int *pInt)
{
   if(pInt != NULL) {
      int i = *pInt;
   }
}

void BadInOptCallee(_In_opt_ int *pInt)
{
   int i = *pInt; // Dereferencing NULL pointer 'pInt'
}

void InOptCaller()
{
   int *pInt = NULL;
   GoodInOptCallee(pInt);
   BadInOptCallee(pInt);
}
```

Visual Studio Code Analysis sprawdza, czy funkcja sprawdza wartość NULL przed uzyskaniem dostępu do buforu.

### <a name="example-the-_out_-annotation"></a>Przykład: \_ \_ adnotacja out

`_Out_` obsługuje typowy scenariusz, w którym jest przenoszona wskaźnik o wartości innej niż NULL, który wskazuje na bufor elementu, a funkcja Inicjuje element. Obiekt wywołujący nie musi inicjować buforu przed wywołaniem; wywoływana funkcja niesie obietnice zwiększenia, aby ją zainicjować przed zwróceniem.

```cpp
void GoodOutCallee(_Out_ int *pInt)
{
   *pInt = 5;
}

void BadOutCallee(_Out_ int *pInt)
{
   // Did not initialize pInt buffer before returning!
}

void OutCaller()
{
   int *pInt = new int;
   GoodOutCallee(pInt);
   BadOutCallee(pInt);
   delete pInt;
}
```

Narzędzie do analizy Visual Studio Code sprawdza, czy obiekt wywołujący przekazuje wskaźnik o wartości innej niż NULL do buforu dla `pInt` i że bufor jest inicjowany przez funkcję przed zwróceniem.

### <a name="example-the-_out_opt_-annotation"></a>Przykład: \_ \_ \_ adnotacja opt out

`_Out_opt_` jest taka sama jak `_Out_` , z tą różnicą, że parametr może mieć wartość null i dlatego funkcja powinna ją sprawdzić.

```cpp
void GoodOutOptCallee(_Out_opt_ int *pInt)
{
   if (pInt != NULL) {
      *pInt = 5;
   }
}

void BadOutOptCallee(_Out_opt_ int *pInt)
{
   *pInt = 5; // Dereferencing NULL pointer 'pInt'
}

void OutOptCaller()
{
   int *pInt = NULL;
   GoodOutOptCallee(pInt);
   BadOutOptCallee(pInt);
}
```

Visual Studio Code Analysis sprawdza, czy ta funkcja sprawdza obecność wartości NULL przed usunięciem `pInt` odwołania, a jeśli `pInt` nie ma wartości null, to bufor zostanie zainicjowany przez funkcję przed zwróceniem.

### <a name="example-the-_inout_-annotation"></a>Przykład: \_ \_ adnotacja Inout

`_Inout_` służy do dodawania adnotacji do parametru wskaźnika, który może zostać zmieniony przez funkcję. Wskaźnik musi wskazywać prawidłowe dane zainicjowane przed wywołaniem, a nawet w przypadku zmiany, musi mieć prawidłową wartość zwracaną. Adnotacja określa, że funkcja może swobodnie odczytywać i zapisywać w buforze jednego elementu. Obiekt wywołujący musi dostarczyć bufor i zainicjować go.

> [!NOTE]
> Podobnie jak `_Out_` , `_Inout_` należy zastosować do modyfikowalnej wartości.

```cpp
void InOutCallee(_Inout_ int *pInt)
{
   int i = *pInt;
   *pInt = 6;
}

void InOutCaller()
{
   int *pInt = new int;
   *pInt = 5;
   InOutCallee(pInt);
   delete pInt;
}

void BadInOutCaller()
{
   int *pInt = NULL;
   InOutCallee(pInt); // 'pInt' should not be NULL
}
```

Visual Studio Code Analysis sprawdza, czy obiekty wywołujące przechodzą wskaźnik o wartości innej niż NULL do zainicjowanego buforu dla `pInt` , i że przed zwróceniem `pInt` nadal jest inne niż null i bufor jest zainicjowany.

### <a name="example-the-_inout_opt_-annotation"></a>Przykład: \_ \_ \_ adnotacja opt Inout

`_Inout_opt_` jest taka sama jak `_Inout_` , z tą różnicą, że parametr wejściowy może mieć wartość null i dlatego funkcja powinna ją sprawdzić.

```cpp
void GoodInOutOptCallee(_Inout_opt_ int *pInt)
{
   if(pInt != NULL) {
      int i = *pInt;
      *pInt = 6;
   }
}

void BadInOutOptCallee(_Inout_opt_ int *pInt)
{
   int i = *pInt; // Dereferencing NULL pointer 'pInt'
   *pInt = 6;
}

void InOutOptCaller()
{
   int *pInt = NULL;
   GoodInOutOptCallee(pInt);
   BadInOutOptCallee(pInt);
}
```

Visual Studio Code Analysis sprawdza, czy ta funkcja sprawdza wartość NULL przed uzyskaniem dostępu do buforu, a jeśli `pInt` nie ma wartości null, to bufor zostanie zainicjowany przez funkcję przed zwróceniem.

### <a name="example-the-_outptr_-annotation"></a>Przykład: \_ \_ adnotacja Outptr

`_Outptr_` służy do dodawania adnotacji do parametru, który jest przeznaczony do zwrócenia wskaźnika.  Sam parametr nie powinien mieć wartości NULL, a wywołana funkcja zwraca wskaźnik o wartości innej niż NULL i wskaźnik wskazuje na zainicjowanie danych.

```cpp
void GoodOutPtrCallee(_Outptr_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 5;

   *pInt = pInt2;
}

void BadOutPtrCallee(_Outptr_ int **pInt)
{
   int *pInt2 = new int;
   // Did not initialize pInt buffer before returning!
   *pInt = pInt2;
}

void OutPtrCaller()
{
   int *pInt = NULL;
   GoodOutPtrCallee(&pInt);
   BadOutPtrCallee(&pInt);
}
```

Visual Studio Code Analysis sprawdza, czy obiekt wywołujący przekazuje wskaźnik o wartości innej niż NULL `*pInt` oraz że bufor jest inicjowany przez funkcję przed zwróceniem.

### <a name="example-the-_outptr_opt_-annotation"></a>Przykład: \_ \_ \_ adnotacja opt Outptr

`_Outptr_opt_` jest taka sama jak `_Outptr_` , z tą różnicą, że parametr jest opcjonalny — obiekt wywołujący może przekazać wskaźnik o wartości null dla parametru.

```cpp
void GoodOutPtrOptCallee(_Outptr_opt_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 6;

   if(pInt != NULL) {
      *pInt = pInt2;
   }
}

void BadOutPtrOptCallee(_Outptr_opt_ int **pInt)
{
   int *pInt2 = new int;
   *pInt2 = 6;
   *pInt = pInt2; // Dereferencing NULL pointer 'pInt'
}

void OutPtrOptCaller()
{
   int **ppInt = NULL;
   GoodOutPtrOptCallee(ppInt);
   BadOutPtrOptCallee(ppInt);
}
```

Visual Studio Code Analysis sprawdza, czy ta funkcja sprawdza obecność wartości NULL przed usunięciem `*pInt` odwołania, oraz że bufor jest inicjowany przez funkcję przed zwróceniem.

### <a name="example-the-_success_-annotation-in-combination-with-_out_"></a>Przykład: \_ \_ adnotacja sukcesów w połączeniu z \_ out\_

Adnotacje można stosować do większości obiektów.  W szczególności można dodać adnotacje do całej funkcji.  Jedną z najbardziej oczywistych cech funkcji jest to, że może ona zakończyć się powodzeniem lub niepowodzeniem. Ale podobnie jak skojarzenie między buforem i jego rozmiarem, język C/C++ nie może wyznaczać sukcesu lub niepowodzenia funkcji Express. Za pomocą `_Success_` adnotacji można wypowiedzieć, jakie sukcesy dla funkcji wyglądają jak.  Parametr do `_Success_` adnotacji jest tylko wyrażeniem, gdy wartość true wskazuje, że funkcja zakończyła się powodzeniem. Wyrażenie może być dowolne, co może obsłużyć Analizator adnotacji. Efekty adnotacji po zwracaniu funkcji są stosowane tylko wtedy, gdy funkcja się powiedzie. W tym przykładzie pokazano `_Success_` , jak współdziała z programem `_Out_` w celu wykonania odpowiednich czynności. Możesz użyć słowa kluczowego, **`return`** aby reprezentować wartość zwracaną.

```cpp
_Success_(return != false) // Can also be stated as _Success_(return)
bool GetValue(_Out_ int *pInt, bool flag)
{
   if(flag) {
      *pInt = 5;
      return true;
   } else {
      return false;
   }
}
```

`_Out_`Adnotacja powoduje, że analiza Visual Studio Code sprawdza, czy obiekt wywołujący przekazuje wskaźnik o wartości innej niż null do buforu dla `pInt` , i że bufor jest inicjowany przez funkcję przed zwróceniem.

## <a name="sal-best-practice"></a>Najlepsze rozwiązanie SAL

### <a name="adding-annotations-to-existing-code"></a>Dodawanie adnotacji do istniejącego kodu

SAL to zaawansowana technologia, która może pomóc w zwiększeniu bezpieczeństwa i niezawodności kodu. Po poznaniu SAL możesz zastosować nową umiejętność do codziennej pracy. W nowym kodzie, można użyć specyfikacji opartych na SAL przez projektowanie w całej organizacji. w starszym kodzie można dodawać adnotacje przyrostowo, a tym samym zwiększać korzyści przy każdej aktualizacji.

Publiczne nagłówki Microsoft są już opatrzone adnotacjami. W związku z tym sugerujemy, aby w swoich projektach były najpierw Adnotuj funkcje węzła liścia i funkcje, które wywołują interfejsy API Win32 w celu uzyskania największej korzyści.

### <a name="when-do-i-annotate"></a>Kiedy mogę dodać adnotację?

Oto kilka wytycznych:

- Adnotuj wszystkie parametry wskaźnika.

- Adnotuj adnotacje zakresu wartości, dzięki czemu Analiza kodu może zapewnić bezpieczeństwo bufora i wskaźnika.

- Dodawanie adnotacji do reguł blokowania i blokowanie efektów ubocznych. Aby uzyskać więcej informacji, zobacz [Dodawanie adnotacji do zachowania blokowania](../code-quality/annotating-locking-behavior.md).

- Dodawanie adnotacji do właściwości sterowników i innych właściwości specyficznych dla domeny.

Można też dodać adnotacje do wszystkich parametrów, aby upewnić się, że zamierzenie jest jasne w całej i aby ułatwić sprawdzenie, czy adnotacje zostały wykonane.

## <a name="see-also"></a>Zobacz też

- [Korzystanie z adnotacji SAL w celu zmniejszenia liczby defektów kodu C/C++](../code-quality/using-sal-annotations-to-reduce-c-cpp-code-defects.md)
- [Dodawanie adnotacji do parametrów funkcji i zwracanych wartości](../code-quality/annotating-function-parameters-and-return-values.md)
- [Zachowanie funkcji dodawania adnotacji](../code-quality/annotating-function-behavior.md)
- [Dodawanie adnotacji struktur i klas](../code-quality/annotating-structs-and-classes.md)
- [Dodawanie adnotacji do zachowania blokującego](../code-quality/annotating-locking-behavior.md)
- [Określanie miejsca i warunków stosowania adnotacji](../code-quality/specifying-when-and-where-an-annotation-applies.md)
- [Najlepsze rozwiązania i przykłady](../code-quality/best-practices-and-examples-sal.md)
