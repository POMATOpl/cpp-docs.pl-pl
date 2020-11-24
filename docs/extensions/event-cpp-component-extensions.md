---
title: Event — słowo kluczowe (C++/CLI i C++/CX)
description: Dowiedz się, jak używać słowa kluczowego rozszerzeń składników języka Microsoft C++ `event` .
ms.date: 11/20/2020
ms.topic: reference
f1_keywords:
- event
- event_cpp
helpviewer_keywords:
- event keyword [C++]
ms.openlocfilehash: 6a2fa97140f747b4afc380b57f8f7c71f08875db
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483246"
---
# <a name="event-keyword-ccli-and-ccx"></a>`event` słowo kluczowe (C++/CLI i C++/CX)

**`event`** Słowo kluczowe deklaruje *zdarzenie*, które jest powiadomieniem do zarejestrowanych subskrybentów *(programy obsługi zdarzeń*), które wystąpiły w wyniku zainteresowania.

## <a name="all-runtimes"></a>Wszystkie środowiska wykonawcze

C++/CX obsługuje deklarowanie *elementu członkowskiego zdarzenia* lub *bloku zdarzeń*. Element członkowski zdarzenia jest skrótem do deklarowania bloku zdarzeń. Domyślnie członek zdarzenia deklaruje `add` funkcje, i, `remove` `raise` które są zadeklarowane jawnie w bloku zdarzenia. Aby dostosować funkcje w składowej zdarzenia, zadeklaruj blok zdarzenia zamiast tego, a następnie zastąp wymagane funkcje.

### <a name="syntax"></a>Składnia

```cpp
// event data member
modifier event delegate^ event_name;

// event block
modifier event delegate^ event_name
{
   modifier return_value add(delegate^ name);
   modifier void remove(delegate^ name);
   modifier void raise(parameters);
}
```

### <a name="parameters"></a>Parametry

*modyfikator*\
Modyfikator, który może być używany w deklaracji zdarzenia lub metodzie dostępu do zdarzeń.  Możliwe wartości to **`static`** i **`virtual`** .

*Wierz*\
[Delegat](delegate-cpp-component-extensions.md), którego sygnatura musi być zgodna z programem obsługi zdarzeń.

*event_name*\
Nazwa zdarzenia.

*return_value*\
Wartość zwracana metody dostępu do zdarzenia.  Aby można było zweryfikować, zwracany typ musi być **`void`** .

*wejściowe*\
obowiązkowe Parametry `raise` metody, które pasują do sygnatury parametru *delegata* .

### <a name="remarks"></a>Uwagi

Zdarzenie jest skojarzeniem między delegatem a *programem obsługi zdarzeń*. Program obsługi zdarzeń jest funkcją członkowską, która reaguje, gdy zdarzenie zostanie wyzwolone. Umożliwia klientom z dowolnej klasy rejestrowanie metod, które pasują do sygnatury i zwracanego typu delegata.

Istnieją dwa rodzaje deklaracji zdarzeń:

*element członkowski danych zdarzenia*\
Kompilator automatycznie tworzy magazyn dla zdarzenia w postaci elementu członkowskiego typu delegata i tworzy `add` funkcje wewnętrzne, `remove` i i `raise` składowe. Składowa danych zdarzenia musi być zadeklarowana wewnątrz klasy. Zwracany typ typu zwracanego delegata musi być zgodny z typem zwracanym programu obsługi zdarzeń.

*blok zdarzeń*\
Blok zdarzeń pozwala jawnie zadeklarować i dostosować zachowanie `add` `remove` metod,, i `raise` .

Możesz użyć `operator +=` i, `operator -=` Aby dodać i usunąć program obsługi zdarzeń, lub wywołać `add` metody i `remove` jawnie.

**`event`** jest kontekstowym słowem kluczowym. Aby uzyskać więcej informacji, zobacz [kontekstowe słowa kluczowe](context-sensitive-keywords-cpp-component-extensions.md).

## <a name="windows-runtime"></a>Środowisko wykonawcze systemu Windows

### <a name="remarks"></a>Uwagi

Aby uzyskać więcej informacji, zobacz [Events (C++/CX)](../cppcx/events-c-cx.md).

Aby dodać lub później usunąć procedurę obsługi zdarzeń, Zapisz `EventRegistrationToken` strukturę zwracaną przez `add` operację. Następnie w `remove` operacji Użyj zapisanej struktury, `EventRegistrationToken` Aby zidentyfikować procedurę obsługi zdarzeń do usunięcia.

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/ZW`

## <a name="common-language-runtime"></a>środowiska uruchomieniowe w trakcie wykonania

Słowo kluczowe **zdarzenia** umożliwia zadeklarowanie zdarzenia. Zdarzenie to sposób, w jaki Klasa dostarcza powiadomienia, gdy wystąpi coś zainteresowania.

### <a name="syntax"></a>Składnia

```cpp
// event data member
modifier event delegate^ event_name;

// event block
modifier event delegate^ event_name
{
   modifier return_value add(delegate^ name);
   modifier void remove(delegate^ name);
   modifier void raise(parameters);
}
```

### <a name="parameters"></a>Parametry

*modyfikator*\
Modyfikator, który może być używany w deklaracji zdarzenia lub metodzie dostępu do zdarzeń.  Możliwe wartości to **`static`** i **`virtual`** .

*Wierz*\
[Delegat](delegate-cpp-component-extensions.md), którego sygnatura musi być zgodna z programem obsługi zdarzeń.

*event_name*\
Nazwa zdarzenia.

*return_value*\
Wartość zwracana metody dostępu do zdarzenia.  Aby można było zweryfikować, zwracany typ musi być **`void`** .

*wejściowe*\
obowiązkowe Parametry `raise` metody, które pasują do sygnatury parametru *delegata* .

### <a name="remarks"></a>Uwagi

Zdarzenie jest skojarzeniem między delegatem a *programem obsługi zdarzeń*. Program obsługi zdarzeń jest funkcją członkowską, która reaguje, gdy zdarzenie zostanie wyzwolone. Umożliwia klientom z dowolnej klasy rejestrowanie metod, które pasują do sygnatury i zwracanego typu obiektu delegowanego.

Delegat może mieć co najmniej jedną skojarzoną metodę. Te metody są wywoływane, gdy kod wskazuje, że zdarzenie wystąpiło. Zdarzenie w jednym programie można udostępnić innym programom przeznaczonym dla .NET Framework środowiska uruchomieniowego języka wspólnego.

Istnieją dwa rodzaje deklaracji zdarzeń:

*elementy członkowskie danych zdarzenia*\
Kompilator tworzy magazyn dla zdarzeń składowych danych jako element członkowski typu delegata. Składowa danych zdarzenia musi być zadeklarowana wewnątrz klasy. Jest on również znany jako *uproszczone zdarzenie*. Zobacz przykład kodu.

*bloki zdarzeń*\
Bloki zdarzeń pozwalają dostosować zachowanie `add` `remove` metod, i `raise` , implementując `add` `remove` metody, i `raise` . Sygnatura `add` `remove` metod, i `raise` musi być zgodna z podpisem delegata. Zdarzenia blokowania zdarzeń nie są elementami członkowskimi danych. Wszelkie użycie jako element członkowski danych generuje błąd kompilatora.

Zwracany typ procedury obsługi zdarzeń musi być zgodny z typem zwracanym delegata.

W .NET Framework można traktować składową danych tak, jakby była to sama metoda (czyli `Invoke` Metoda odpowiedniego delegata). W tym celu należy wstępnie zdefiniować typ delegata do deklarowania elementu członkowskiego danych zdarzenia zarządzanego. W przeciwieństwie do zarządzanej metody zdarzenia niejawnie definiuje odpowiadającą zarządzaną delegata, jeśli nie jest jeszcze zdefiniowana. Przykład zawiera przykładowy kod na końcu tego artykułu.

Podczas deklarowania zdarzenia zarządzanego można określić `add` i `remove` metody dostępu, które będą wywoływane, gdy programy obsługi zdarzeń zostaną dodane lub usunięte przy użyciu operatorów **`+=`** i **`-=`** . `add`Metody, `remove` i `raise` mogą być wywoływane jawnie.

Aby tworzyć i używać zdarzeń w programie Microsoft C++, należy wykonać następujące czynności:

1. Utwórz lub Zidentyfikuj delegata. Jeśli tworzysz własne zdarzenie, musisz również upewnić się, że istnieje delegat do użycia ze **`event`** słowem kluczowym. Jeśli zdarzenie jest wstępnie zdefiniowane, w .NET Framework na przykład, odbiorcy zdarzenia muszą znać nazwę delegata.

2. Utwórz klasę zawierającą:

   - Zdarzenie utworzone na podstawie delegata.

   - Obowiązkowe Metoda, która sprawdza, czy wystąpienie delegata zadeklarowane za pomocą **`event`** słowa kluczowego istnieje. W przeciwnym razie logika musi być umieszczona w kodzie, który uruchamia zdarzenie.

   - Metody wywołujące zdarzenie. Metody te można zastępować w niektórych funkcjach klasy podstawowej.

   Ta klasa definiuje zdarzenie.

3. Zdefiniuj co najmniej jedną klasę, która łączy metody ze zdarzeniem. Każda z tych klas spowoduje skojarzenie jednej lub więcej metod ze zdarzeniem w klasie bazowej.

4. Użyj zdarzenia:

   - Utwórz obiekt klasy, która zawiera deklarację zdarzenia.

   - Utwórz obiekt klasy, która zawiera definicję zdarzenia.

Aby uzyskać więcej informacji o zdarzeniach/CLI języka C++, zobacz [zdarzenia w interfejsie](../dotnet/how-to-use-events-in-cpp-cli.md).

### <a name="requirements"></a>Wymagania

Opcja kompilatora: `/clr`

### <a name="examples"></a>Przykłady

Poniższy przykład kodu ilustruje deklarowanie par delegatów, zdarzeń i programów obsługi zdarzeń. Pokazuje, jak subskrybować (dodawać), wywoływać, a następnie anulować subskrypcję (usunąć) obsługi zdarzeń.

```cpp
// mcppv2_events.cpp
// compile with: /clr
using namespace System;

// declare delegates
delegate void ClickEventHandler(int, double);
delegate void DblClickEventHandler(String^);

// class that defines events
ref class EventSource {
public:
   event ClickEventHandler^ OnClick;   // declare the event OnClick
   event DblClickEventHandler^ OnDblClick;   // declare OnDblClick

   void FireEvents() {
      // raises events
      OnClick(7, 3.14159);
      OnDblClick("Hello");
   }
};

// class that defines methods that will called when event occurs
ref class EventReceiver {
public:
   void OnMyClick(int i, double d) {
      Console::WriteLine("OnClick: {0}, {1}", i, d);
   }

   void OnMyDblClick(String^ str) {
      Console::WriteLine("OnDblClick: {0}", str);
   }
};

int main() {
   EventSource ^ MyEventSource = gcnew EventSource();
   EventReceiver^ MyEventReceiver = gcnew EventReceiver();

   // hook handler to event
   MyEventSource->OnClick += gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);
   MyEventSource->OnDblClick += gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);

   // invoke events
   MyEventSource->FireEvents();

   // unhook handler to event
   MyEventSource->OnClick -= gcnew ClickEventHandler(MyEventReceiver, &EventReceiver::OnMyClick);
   MyEventSource->OnDblClick -= gcnew DblClickEventHandler(MyEventReceiver, &EventReceiver::OnMyDblClick);
}
```

```Output
OnClick: 7, 3.14159

OnDblClick: Hello
```

Poniższy przykład kodu demonstruje logikę używaną do generowania `raise` metody prostego zdarzenia. Jeśli zdarzenie ma jednego lub więcej subskrybentów, wywoływanie `raise` metody niejawnie lub jawnie wywołuje delegata. Jeśli typ zwracany delegata nie jest **`void`** i jeśli nie istnieją Subskrybenci zdarzeń, `raise` Metoda zwraca wartość domyślną dla typu delegata. Jeśli nie ma subskrybentów zdarzeń, wywołanie `raise` metody natychmiast zwraca i żaden wyjątek nie zostanie zgłoszony. Jeśli typem zwracanym delegata nie jest **`void`** , zwracany jest typ delegata.

```cpp
// trivial_events.cpp
// compile with: /clr /c
using namespace System;
public delegate int Del();
public ref struct C {
   int i;
   event Del^ MyEvent;

   void FireEvent() {
      i = MyEvent();
   }
};

ref struct EventReceiver {
   int OnMyClick() { return 0; }
};

int main() {
   C c;
   c.i = 687;

   c.FireEvent();
   Console::WriteLine(c.i);
   c.i = 688;

   EventReceiver^ MyEventReceiver = gcnew EventReceiver();
   c.MyEvent += gcnew Del(MyEventReceiver, &EventReceiver::OnMyClick);
   Console::WriteLine(c.i);
}
```

```Output
0

688
```

## <a name="see-also"></a>Zobacz także

[Rozszerzenia składników dla platformy .NET i platformy uniwersalnej systemu Windows](component-extensions-for-runtime-platforms.md)
