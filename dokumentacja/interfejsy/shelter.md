# Shelter

```csharp
namespace shelter.Interfaces.Shelter
{
    /// <summary>
    /// Interfejs do zarządzania operacjami związanymi ze schroniskiem w systemie.
    /// </summary>
    public interface IShelterService
    {
        /// <summary>
        /// Tworzy konto schroniska na podstawie podanego adresu e-mail.
        /// </summary>
        /// <param name="email">Adres e-mail schroniska.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca dane logowania schroniska.</returns>
        Task<ShelterLoginDto> CreateAccount(string email);

        /// <summary>
        /// Tworzy nowe schronisko w systemie na podstawie podanego adresu e-mail.
        /// </summary>
        /// <param name="email">Adres e-mail schroniska.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli schronisko zostało pomyślnie utworzone.</returns>
        Task<bool> CreateUserShelter(string email);

        /// <summary>
        /// Generuje ciąg tokena dla schroniska na podstawie danych logowania.
        /// </summary>
        /// <param name="shelter">Dane logowania schroniska.</param>
        /// <returns>Ciąg tokena dostępu do zasobów systemu.</returns>
        string GenerateTokenString(ShelterLoginDto shelter);

        /// <summary>
        /// Loguje schronisko do systemu na podstawie podanych danych logowania.
        /// </summary>
        /// <param name="shelter">Dane logowania schroniska.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli logowanie schroniska przebiegło pomyślnie.</returns>
        Task<bool> LoginUser(ShelterLoginDto shelter);

        /// <summary>
        /// Dodaje dodatkowe informacje o schronisku do systemu.
        /// </summary>
        /// <param name="shelterForm">Formularz zawierający dodatkowe informacje o schronisku.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli informacje o schronisku zostały pomyślnie dodane.</returns>
        Task<bool> AddShelterDetailsForm(ShelterForm shelterForm);

        /// <summary>
        /// Pobiera listę zwierząt należących do danego schroniska na podstawie adresu e-mail schroniska.
        /// </summary>
        /// <param name="shelterEmail">Adres e-mail schroniska.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę zwierząt należących do schroniska.</returns>
        Task<List<PetsBelongsToShelterDto>> GetAllPetsBelongsToShelter(string shelterEmail);

        /// <summary>
        /// Pobiera listę psów należących do danego schroniska na podstawie adresu e-mail schroniska.
        /// </summary>
        /// <param name="shelterEmail">Adres e-mail schroniska.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę psów należących do schroniska.</returns>
        Task<List<PetsBelongsToShelterDto>> GetAllDogsBelongsToShelter(string shelterEmail);

        /// <summary>
        /// Pobiera listę kotów należących do danego schroniska na podstawie adresu e-mail schroniska.
        /// </summary>
        /// <param name="shelterEmail">Adres e-mail schroniska.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę kotów należących do schroniska.</returns>
        Task<List<PetsBelongsToShelterDto>> GetAllCatsBelongsToShelter(string shelterEmail);

        /// <summary>
        /// Pobiera listę gryzoni należących do danego schroniska na podstawie adresu e-mail schroniska.
        /// </summary>
        /// <param name="shelterEmail">Adres e-mail schroniska.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę gryzoni należących do schroniska.</returns>
        Task<List<PetsBelongsToShelterDto>> GetAllRodentsBelongsToShelter(string shelterEmail);

        /// <summary>
        /// Pobiera listę innych zwierząt (nie psów, kotów ani gryzoni) należących do danego schroniska na podstawie adresu e-mail schroniska.
        /// </summary>
        /// <param name="shelterEmail">Adres e-mail schroniska.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę innych zwierząt należących do schroniska.</returns>
        Task<List<PetsBelongsToShelterDto>> GetOthersBelongsToShelter(string shelterEmail);

        /// <summary>
        /// Pobiera informacje o danym schronisku na podstawie adresu e-mail schroniska.
        /// </summary>
        /// <param name="shelterEmail">Adres e-mail schroniska.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca formularz informacji o schronisku.</returns>
        Task<ShelterForm> GetSingleShelter(string shelterEmail);

        /// <summary>
        /// Wysyła żądanie zresetowania hasła przez schronisko.
        /// </summary>
        /// <param name="resetPasswordReqModel">Dane dotyczące żądania zresetowania hasła.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną.</returns>
        Task<string> ResetPassworReq(ResetPasswordReqModel resetPasswordReqModel);

        /// <summary>
        /// Resetuje hasło schroniska na podstawie dostarczonych danych.
        /// </summary>
        /// <param name="resetPasswordModel">Dane do zresetowania hasła schroniska.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli hasło zostało pomyślnie zresetowane.</returns>
        Task<bool> ResetPassword(ResetPasswordModel resetPasswordModel);
    }

}
```



### ShelterForm

Klasa `ShelterForm` jest modelem danych, który zbiera informacje od schroniska dotyczące warunków jakie użytkownik gotowy do adopcjizwierząt musi spełnić.

1. **Name**
   * _Typ: string_
   * _Opis: Reprezentuje nazwę schroniska._
2. **Email**
   * _Typ: string_
   * _Opis: Reprezentuje adres e-mail schroniska._
3. **Phone**
   * _Typ: string_
   * _Opis: Reprezentuje numer telefonu schroniska._
4. **PostCode**
   * _Typ: string_
   * _Opis: Reprezentuje kod pocztowy miejsca schroniska._
5. **Town**
   * _Typ: string_
   * _Opis: Reprezentuje miejscowość, w której znajduje się schronisko._
6. **Adress**
   * _Typ: string_
   * _Opis: Reprezentuje dokładny adres schroniska._
7. **Url**
   * _Typ: string_
   * _Opis: Reprezentuje adres URL, jeśli schronisko posiada stronę internetową._
8. **IncomeSource**
   * _Typ: bool?_
   * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje o źródle dochodu użytkownika._
9. **Lifestyle**
   * _Typ: bool?_
   * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje na temat stylu życia użytkownika._
10. **HousingType**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje na temat rodzaju mieszkania użytkownika._
11. **HouseOwner**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje, czy użytkownik jest właścicielem domu._
12. **HoursAlone**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje na temat ilości godzin, jakie zwierzęta spędzają same._
13. **Floor**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje na temat piętra, na którym znajduje się mieszkanie użytkownika._
14. **Elevator**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje, czy w budynku znajduje się winda._
15. **WalksNumber**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje na temat liczby spacerów, jakie zwierzęta otrzymują dziennie._
16. **WalksTime**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje na temat czasu trwania spaceru dla zwierząt._
17. **Fence**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje, czy wokół miejsca zamieszkania użytkownika jest ogrodzenie._
18. **FenceHeight**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje na temat wysokości ogrodzenia wokół miejsca zamieszkania użytkownika._
19. **PropertySize**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje na temat rozmiaru nieruchomości, na której znajduje się mieszkanie użytkownika._
20. **PetPlace**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje, czy użytkownik ma odpowiednie miejsce dla zwierząt w domu._
21. **PetPlaceAlone**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje, czy zwierzęta będą miały odpowiednie miejsce, gdy użytkownik nie będzie w domu._
22. **CareAlone**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje na temat planu opieki nad zwierzętami, gdy użytkownik nie będzie w domu._
23. **HouseMates**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje na temat innych mieszkańców domu._
24. **Animals**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje, czy w miejscu zamieszkania użytkownika są już inne zwierzęta._
25. **AnimalsBefore**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać informacje, czy użytkownik miał wcześniej inne zwierzęta._
26. **AnimalsBeforeText**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać dodatkowy tekst opisujący doświadczenia użytkownika ze zwierzętami._
27. **Text**
    * _Typ: bool?_
    * _Opis: Reprezentuje informację, czy schronisko chce uzyskać dodatkowy tekst lub uwagi od użytkownika._

### ShelterLoginDto

Klasa `ShelterLoginDto` jest modelem danych, który zawiera informacje niezbędne do uwierzytelnienia schroniska.

1. **EmailShelter**
   * _Typ: string_
   * _Opis: Reprezentuje adres e-mail schroniska, który jest używany do uwierzytelnienia._
2. **PasswordShelter**
   * _Typ: string_
   * _Opis: Reprezentuje hasło schroniska, które jest używane do uwierzytelnienia._
