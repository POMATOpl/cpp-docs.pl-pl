---
description: 'Dowiedz się więcej o: odbicie (C++/CLI)'
title: Odbicie (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- typeid keyword [C++]
- reflection [C++}, about reflection
- metadata, reflection
- GetType method
- .NET Framework [C++], reflection
- data types [C++], reflection
- reflection [C++}
- plug-ins [C++]
- reflection [C++}, plug-ins
- assemblies [C++], enumerating data types in
- public types [C++]
- reflection [C++], external assemblies
- assemblies [C++]
- data types [C++], enumerating
- public members [C++]
ms.assetid: 46b6ff4a-e441-4022-8892-78e69422f230
ms.openlocfilehash: a3a9a33a239ec678279455ea41b7c60749cc0189
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: pl-PL
ms.lasthandoff: 12/11/2020
ms.locfileid: "97245801"
---
# <a name="reflection-ccli"></a>Odbicie (C++/CLI)

Odbicie umożliwia inspekcję znanych typów danych w czasie wykonywania. Odbicie umożliwia Wyliczenie typów danych w danym zestawie, a elementy członkowskie danej klasy lub typu wartości mogą zostać odnalezione. Ta wartość jest prawdziwa niezależnie od tego, czy typ był znany, czy przywoływany w czasie kompilacji. Dzięki temu odbicie jest przydatne dla narzędzi do programowania i zarządzania kodem.

Należy zauważyć, że podana nazwa zestawu jest silną nazwą (zobacz [Tworzenie i używanie zestawów Strong-Named](/dotnet/framework/app-domains/create-and-use-strong-named-assemblies)), które obejmują wersję zestawu, kulturę i informacje dotyczące podpisywania. Należy również zauważyć, że nazwa przestrzeni nazw, w której jest zdefiniowany typ danych, może być pobierana wraz z nazwą klasy bazowej.

Najbardziej typowym sposobem na dostęp do funkcji odbicia jest użycie <xref:System.Object.GetType%2A> metody. Ta metoda jest dostarczana przez <xref:System.Object?displayProperty=nameWithType> , z której wszystkie klasy są gromadzone jako pochodne.

> [!NOTE]
> Odbicie w pliku. exe utworzonym za pomocą kompilatora języka Microsoft C++ jest dozwolone tylko wtedy, gdy plik. exe jest skompilowany z **opcją/CLR: Pure** lub **/CLR: Safe** kompilatora. **/CLR: Pure** i **/CLR:** opcje kompilatora bezpiecznego są przestarzałe w programie Visual Studio 2015 i niedostępne w programie Visual Studio 2017. Zobacz [/CLR (Kompilacja środowiska uruchomieniowego języka wspólnego)](../build/reference/clr-common-language-runtime-compilation.md) , aby uzyskać więcej informacji.

Aby uzyskać więcej informacji, zobacz <xref:System.Reflection>.

## <a name="example-gettype"></a>Przykład: GetType

`GetType`Metoda zwraca wskaźnik do <xref:System.Type> obiektu klasy, który opisuje typ, gdy oparty jest obiekt. (Obiekt **Type** nie zawiera żadnych informacji specyficznych dla wystąpienia). Jeden z tych elementów jest pełną nazwą typu, który może być wyświetlany w następujący sposób:

Należy zauważyć, że nazwa typu zawiera pełen zakres, w którym jest zdefiniowany typ, łącznie z przestrzenią nazw i jest wyświetlana w składni platformy .NET, z kropką jako operatorem rozpoznawania zakresu.

```cpp
// vcpp_reflection.cpp
// compile with: /clr
using namespace System;
int main() {
   String ^ s = "sample string";
   Console::WriteLine("full type name of '{0}' is '{1}'", s, s->GetType());
}
```

```Output
full type name of 'sample string' is 'System.String'
```

## <a name="example-boxed-value-types"></a>Przykład: opakowane typy wartości

Typy wartości mogą być również używane z `GetType` funkcją, ale muszą być najpierw opakowane.

```cpp
// vcpp_reflection_2.cpp
// compile with: /clr
using namespace System;
int main() {
   Int32 i = 100;
   Object ^ o = i;
   Console::WriteLine("type of i = '{0}'", o->GetType());
}
```

```Output
type of i = 'System.Int32'
```

## <a name="example-typeid"></a>Przykład: typeid

Podobnie jak w przypadku `GetType` metody operator [typeid](../extensions/typeid-cpp-component-extensions.md) zwraca wskaźnik do obiektu **typu** , więc ten kod wskazuje nazwę typu **System. Int32**. Wyświetlanie nazw typów to najbardziej podstawowa funkcja odbicia, ale potencjalnie bardziej użyteczna Technika polega na sprawdzeniu lub znalezieniu prawidłowych wartości dla typów wyliczeniowych. Można to zrobić przy użyciu statycznego **wyliczenia:: GetNames** , która zwraca tablicę ciągów, z których każda zawiera wartość wyliczenia w postaci tekstowej.  Poniższy przykład pobiera tablicę ciągów opisującą wartości wyliczenia wartości dla wyliczenia **opcji** (CLR) i wyświetla je w pętli.

Jeśli czwarta opcja zostanie dodana do wyliczenia **opcji** , ten kod zgłosi nową opcję bez ponownej kompilacji, nawet jeśli Wyliczenie jest zdefiniowane w osobnym zestawie.

```cpp
// vcpp_reflection_3.cpp
// compile with: /clr
using namespace System;

enum class Options {   // not a native enum
   Option1, Option2, Option3
};

int main() {
   array<String^>^ names = Enum::GetNames(Options::typeid);

   Console::WriteLine("there are {0} options in enum '{1}'",
               names->Length, Options::typeid);

   for (int i = 0 ; i < names->Length ; i++)
      Console::WriteLine("{0}: {1}", i, names[i]);

   Options o = Options::Option2;
   Console::WriteLine("value of 'o' is {0}", o);
}
```

```Output
there are 3 options in enum 'Options'
0: Option1
1: Option2
2: Option3
value of 'o' is Option2
```

## <a name="example-gettype-members-and-properties"></a>Przykład: elementy członkowskie i właściwości GetType

`GetType`Obiekt obsługuje wiele elementów członkowskich i właściwości, których można użyć do badania typu. Ten kod pobiera i wyświetla niektóre z tych informacji:

```cpp
// vcpp_reflection_4.cpp
// compile with: /clr
using namespace System;
int main() {
   Console::WriteLine("type information for 'String':");
   Type ^ t = String::typeid;

   String ^ assemblyName = t->Assembly->FullName;
   Console::WriteLine("assembly name: {0}", assemblyName);

   String ^ nameSpace = t->Namespace;
   Console::WriteLine("namespace: {0}", nameSpace);

   String ^ baseType = t->BaseType->FullName;
   Console::WriteLine("base type: {0}", baseType);

   bool isArray = t->IsArray;
   Console::WriteLine("is array: {0}", isArray);

   bool isClass = t->IsClass;
   Console::WriteLine("is class: {0}", isClass);
}
```

```Output
type information for 'String':
assembly name: mscorlib, Version=1.0.5000.0, Culture=neutral,
PublicKeyToken=b77a5c561934e089
namespace: System
base type: System.Object
is array: False
is class: True
```

## <a name="example-enumeration-of-types"></a>Przykład: Wyliczenie typów

Odbicie umożliwia również Wyliczenie typów wewnątrz zestawu i elementów członkowskich w klasach. Aby zademonstrować tę funkcję, zdefiniuj prostą klasę:

```cpp
// vcpp_reflection_5.cpp
// compile with: /clr /LD
using namespace System;
public ref class TestClass {
   int m_i;
public:
   TestClass() {}
   void SimpleTestMember1() {}
   String ^ SimpleMember2(String ^ s) { return s; }
   int TestMember(int i) { return i; }
   property int Member {
      int get() { return m_i; }
      void set(int i) { m_i = i; }
   }
};
```

## <a name="example-inspection-of-assemblies"></a>Przykład: Inspekcja zestawów

Jeśli powyższy kod jest kompilowany do biblioteki DLL o nazwie vcpp_reflection_6.dll, można użyć odbicia, aby sprawdzić zawartość tego zestawu. Obejmuje to użycie statycznego interfejsu API odbicia linki XREF: System. odbicie. Assembly. Load% 2A? displayProperty = nameWithType w celu załadowania zestawu. Ta funkcja zwraca adres obiektu **zestawu** , który można następnie wykonać zapytania o moduły i typy w.

Po pomyślnym załadowaniu zestawu przez system odbicia tablica obiektów **typu** jest pobierana z <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=nameWithType> funkcją. Każdy element tablicy zawiera informacje o innym typie, chociaż w tym przypadku zdefiniowana jest tylko jedna Klasa. Przy użyciu pętli każdy **Typ** w tej tablicy jest pytany o składowe typu przy użyciu funkcji **Type:: GetMembers** . Ta funkcja zwraca tablicę obiektów **MethodInfo** , każdy obiekt zawierający informacje o funkcji składowej, składowej danych lub właściwości w typie.

Należy zauważyć, że lista metod zawiera funkcje jawnie zdefiniowane w **TestClass** i funkcje niejawnie dziedziczone z klasy **System:: Object** . W ramach procedury opisanej w programie .NET, a nie w składni Visual C++, właściwości są wyświetlane jako podstawowy element członkowski danych, do którego uzyskuje dostęp za pomocą funkcji get/set. Funkcje get/set są wyświetlane na tej liście jako metody regularne. Odbicie jest obsługiwane przez środowisko uruchomieniowe języka wspólnego, a nie przez kompilator języka Microsoft C++.

Chociaż ten kod został użyty do sprawdzenia zdefiniowanego zestawu, można również użyć tego kodu do sprawdzenia zestawów .NET. Na przykład jeśli zmienisz TestAssembly na mscorlib, zobaczysz listę każdego typu i metody zdefiniowanej w mscorlib.dll.

```cpp
// vcpp_reflection_6.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;
using namespace System::Reflection;
int main() {
   Assembly ^ a = nullptr;
   try {
      // load assembly -- do not use file extension
      // will look for .dll extension first
      // then .exe with the filename
      a = Assembly::Load("vcpp_reflection_5");
   }
   catch (FileNotFoundException ^ e) {
      Console::WriteLine(e->Message);
      return -1;
   }

   Console::WriteLine("assembly info:");
   Console::WriteLine(a->FullName);
   array<Type^>^ typeArray = a->GetTypes();

   Console::WriteLine("type info ({0} types):", typeArray->Length);

   int totalTypes = 0;
   int totalMembers = 0;
   for (int i = 0 ; i < typeArray->Length ; i++) {
      // retrieve array of member descriptions
      array<MemberInfo^>^ member = typeArray[i]->GetMembers();

      Console::WriteLine("  members of {0} ({1} members):",
      typeArray[i]->FullName, member->Length);
      for (int j = 0 ; j < member->Length ; j++) {
         Console::Write("       ({0})",
         member[j]->MemberType.ToString() );
         Console::Write("{0}  ", member[j]);
         Console::WriteLine("");
         totalMembers++;
      }
      totalTypes++;
   }
   Console::WriteLine("{0} total types, {1} total members",
   totalTypes, totalMembers);
}
```

## <a name="how-to-implement-a-plug-in-component-architecture-using-reflection"></a><a name="implement"></a> Instrukcje: implementowanie architektury składników Plug-In przy użyciu odbicia

W poniższych przykładach kodu przedstawiono sposób użycia odbicia w celu zaimplementowania prostej architektury "wtyczki". Pierwsza lista to aplikacja, a druga to wtyczka. Aplikacja jest formularzem zawierającym wiele dokumentów, który wypełnia siebie przy użyciu dowolnych klas opartych na formularzach, które znajdują się w pliku DLL wtyczki podanej jako argument wiersza polecenia.

Aplikacja próbuje załadować podany zestaw przy użyciu <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> metody. Jeśli to się powiedzie, typy wewnątrz zestawu są wyliczane przy użyciu <xref:System.Reflection.Assembly.GetTypes%2A?displayProperty=fullName> metody. Każdy typ jest następnie sprawdzany pod kątem zgodności przy użyciu <xref:System.Type.IsAssignableFrom%2A?displayProperty=fullName> metody. W tym przykładzie klasy, które znajdują się w podanym zestawie, muszą pochodzić od klasy, aby można było <xref:System.Windows.Forms.Form> zakwalifikować jako wtyczkę.

Klasy zgodne są następnie tworzone przy użyciu <xref:System.Activator.CreateInstance%2A?displayProperty=fullName> metody, która akceptuje <xref:System.Type> jako argument i zwraca wskaźnik do nowego wystąpienia. Każde nowe wystąpienie jest następnie dołączane do formularza i wyświetlane.

Należy zauważyć, że <xref:System.Reflection.Assembly.Load%2A> Metoda nie akceptuje nazw zestawów, które zawierają rozszerzenie pliku. Funkcja Main w aplikacji przycina wszelkie udostępnione rozszerzenia, więc Poniższy przykład kodu działa w obu przypadkach.

### <a name="example"></a>Przykład

Poniższy kod definiuje aplikację akceptującą wtyczki. Nazwa zestawu musi być podana jako pierwszy argument. Ten zestaw powinien zawierać co najmniej jeden publiczny <xref:System.Windows.Forms.Form> Typ pochodny.

```cpp
// plugin_application.cpp
// compile with: /clr /c
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;

ref class PluggableForm : public Form  {
public:
   PluggableForm() {}
   PluggableForm(Assembly^ plugAssembly) {
      Text = "plug-in example";
      Size = Drawing::Size(400, 400);
      IsMdiContainer = true;

      array<Type^>^ types = plugAssembly->GetTypes( );
      Type^ formType = Form::typeid;

      for (int i = 0 ; i < types->Length ; i++) {
         if (formType->IsAssignableFrom(types[i])) {
            // Create an instance given the type description.
            Form^ f = dynamic_cast<Form^> (Activator::CreateInstance(types[i]));
            if (f) {
               f->Text = types[i]->ToString();
               f->MdiParent = this;
               f->Show();
            }
         }
      }
   }
};

int main() {
   Assembly^ a = Assembly::LoadFrom("plugin_application.exe");
   Application::Run(gcnew PluggableForm(a));
}
```

### <a name="example"></a>Przykład

Poniższy kod definiuje trzy klasy pochodne od <xref:System.Windows.Forms.Form> . Gdy nazwa wynikowej nazwy zestawu jest przenoszona do pliku wykonywalnego na poprzedniej liście, każda z tych trzech klas zostanie odnaleziona i zostanie utworzona, pomimo faktu, że były one nieznane dla aplikacji hostingowej w czasie kompilacji.

```cpp
// plugin_assembly.cpp
// compile with: /clr /LD
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Windows::Forms;
using namespace System::Reflection;
using namespace System::Drawing;

public ref class BlueForm : public Form {
public:
   BlueForm() {
      BackColor = Color::Blue;
   }
};

public ref class CircleForm : public Form {
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      args->Graphics->FillEllipse(Brushes::Green, ClientRectangle);
   }
};

public ref class StarburstForm : public Form {
public:
   StarburstForm(){
      BackColor = Color::Black;
   }
protected:
   virtual void OnPaint(PaintEventArgs^ args) override {
      Pen^ p = gcnew Pen(Color::Red, 2);
      Random^ r = gcnew Random( );
      Int32 w = ClientSize.Width;
      Int32 h = ClientSize.Height;
      for (int i=0; i<100; i++) {
         float x1 = w / 2;
         float y1 = h / 2;
         float x2 = r->Next(w);
         float y2 = r->Next(h);
         args->Graphics->DrawLine(p, x1, y1, x2, y2);
      }
   }
};
```

## <a name="how-to-enumerate-data-types-in-assemblies-using-reflection"></a><a name="enumerate"></a> Instrukcje: wyliczanie typów danych w zestawach przy użyciu odbicia

Poniższy kod ilustruje Wyliczenie typów publicznych i członków przy użyciu <xref:System.Reflection> .

Pod nazwą zestawu, w katalogu lokalnym lub w pamięci GAC, poniższy kod próbuje otworzyć zestaw i pobrać opisy. Jeśli to się powiedzie, każdy typ jest wyświetlany z jego publicznymi elementami członkowskimi.

Należy pamiętać, że <xref:System.Reflection.Assembly.Load%2A?displayProperty=fullName> nie są używane żadne rozszerzenia pliku. W związku z tym użycie "mscorlib.dll" jako argumentu wiersza polecenia zakończy się niepowodzeniem, podczas gdy użycie tylko "mscorlib" spowoduje wyświetlenie typu .NET Framework. Jeśli nie podano nazwy zestawu, kod wykryje i zgłosi typy w bieżącym zestawie (plik EXE wynikający z tego kodu).

### <a name="example"></a>Przykład

```cpp
// self_reflection.cpp
// compile with: /clr
using namespace System;
using namespace System::Reflection;
using namespace System::Collections;

public ref class ExampleType {
public:
   ExampleType() {}
   void Func() {}
};

int main() {
   String^ delimStr = " ";
   array<Char>^ delimiter = delimStr->ToCharArray( );
   array<String^>^ args = Environment::CommandLine->Split( delimiter );

// replace "self_reflection.exe" with an assembly from either the local
// directory or the GAC
   Assembly^ a = Assembly::LoadFrom("self_reflection.exe");
   Console::WriteLine(a);

   int count = 0;
   array<Type^>^ types = a->GetTypes();
   IEnumerator^ typeIter = types->GetEnumerator();

   while ( typeIter->MoveNext() ) {
      Type^ t = dynamic_cast<Type^>(typeIter->Current);
      Console::WriteLine("   {0}", t->ToString());

      array<MemberInfo^>^ members = t->GetMembers();
      IEnumerator^ memberIter = members->GetEnumerator();
      while ( memberIter->MoveNext() ) {
         MemberInfo^ mi = dynamic_cast<MemberInfo^>(memberIter->Current);
         Console::Write("      {0}", mi->ToString( ) );
         if (mi->MemberType == MemberTypes::Constructor)
            Console::Write("   (constructor)");

         Console::WriteLine();
      }
      count++;
   }
   Console::WriteLine("{0} types found", count);
}
```

## <a name="see-also"></a>Zobacz także

- [Programowanie .NET w języku C++/interfejsie wiersza polecenia (Visual C++)](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
