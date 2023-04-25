---
description: Technologie i serwisy, których planujemy użyć przy tworzeniu aplikacji.
---

# 🛠 Technologie

<details>

<summary>JavaScript - FRONT</summary>

Vue.js

</details>

### C# - Backend

<details>

<summary>Frameworki</summary>

### EF CORE

Entity Framework Core (EF Core) to narzędzie dla języka C#, które umożliwia programistom manipulowanie danymi w bazie danych.&#x20;

EF Core pozwala na mapowanie obiektów w kodzie na odpowiednie obiekty w bazie danych, dzięki czemu programiści mogą pracować z danymi za pomocą języka C#.&#x20;

Jest to otwartoźródłowy projekt stworzony przez Microsoft.

Programiści definiują modele obiektów, a EF Core tworzy schemat bazy danych z tych modeli.

```
// "Entity Framework Core in Action" autorstwa Jona Smitha
 - rozdział 1: 
"Introducing Entity Framework Core"
```

### ASP.NET CORE

.NET Core to otwarte oprogramowanie, które umożliwia tworzenie aplikacji internetowych, w tym REST API, na różnych systemach operacyjnych

REST API to interfejs programowania aplikacji, który umożliwia komunikację między różnymi systemami i aplikacjami za pomocą protokołu HTTP.

ASP.NET Core to framework, który zapewnia narzędzia i biblioteki do budowania aplikacji internetowych i REST API.&#x20;

```
// "Building RESTful Web APIs with .NET Core" autorstwa Iriny Scurtu 
```

Ten modułowy framework oferuje wiele funkcji, takich jak obsługa żądań HTTP, routowanie, logowanie, autoryzacja i uwierzytelnianie, testowanie jednostkowe i wiele innych.

</details>

{% hint style="success" %}
Zalety C#
{% endhint %}

{% tabs %}
{% tab title="Łatwość użycia" %}
Zapewnia łatwy i prosty sposób tworzenia aplikacji bazodanowych.&#x20;

{% hint style="info" %}
W C# korzystając z wbudowanych frameworków wystarczy zdefiniować klasy reprezentujące modele danych, a EF Core automatycznie tworzy dla nich odpowiednie tabele w bazie danych.
{% endhint %}
{% endtab %}

{% tab title="Wysoka wydajność" %}
Język ten zapewnia wysoką wydajność i szybkość przetwarzania danych.

{% hint style="info" %}
EF Core wykorzystuje cache'owanie wyników, co pozwala na szybsze przetwarzanie zapytań do bazy danych.
{% endhint %}
{% endtab %}

{% tab title="Wsparcie dla wielu baz danych" %}
Obsługuje wiele popularnych baz danych, takich jak SQL Server, MySQL, Oracle, itp

{% hint style="info" %}
EF Core umożliwia tworzenie migracji do różnych baz danych, co ułatwia pracę z różnymi systemami baz danych.
{% endhint %}
{% endtab %}

{% tab title="Bezpieczeństwo" %}
Zapewnia wiele funkcji zabezpieczeń, między innymi walidacja danych i uwierzytelnianie użytkowników.

{% hint style="info" %}
umożliwia definiowanie ograniczeń dla danych w tabelach, co zwiększa bezpieczeństwo aplikacji bazodanowych.
{% endhint %}
{% endtab %}

{% tab title="Łatwość testowania" %}
Dostarcza wiele narzędzi do testowania aplikacji, w tym narzędzia do generowania danych testowych.
{% endtab %}
{% endtabs %}

{% hint style="danger" %}
Wady C#
{% endhint %}

{% tabs %}
{% tab title="Kompleksowość " %}
Jest dość złożonym narzędziem, co może powodować trudności dla początkujących użytkowników

{% hint style="info" %}
C# wraz z EF Core wymaga znajomości języka LINQ oraz konfiguracji połączenia z bazą danych.
{% endhint %}
{% endtab %}

{% tab title="Brak pełnej kontroli" %}
Oferuje wiele domyślnych ustawień i ograniczeń, co może ograniczać kontrolę użytkownika nad aplikacją bazodanową

{% hint style="info" %}
EF Core automatycznie generuje klucze główne dla tabel, co może prowadzić do problemów z kontrolią procesu tworzenia identyfikatorów rekordów.
{% endhint %}
{% endtab %}

{% tab title="Problemy z migracją" %}
może mieć problemy z migracją danych między różnymi wersjami bazy danych.

{% hint style="info" %}
EF Core może mieć trudności z migracją danych, jeśli baza danych została zmieniona poza narzędziem EF Core.
{% endhint %}
{% endtab %}
{% endtabs %}

<details>

<summary>SQL</summary>

Microsoft SQL Server

</details>

<details>

<summary>GitHub</summary>



</details>

<details>

<summary>Azure DevOps</summary>



</details>

<details>

<summary>Bootstrap</summary>



</details>
