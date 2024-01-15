# User

```csharp
 namespace shelter.Interfaces.User
{
    /// <summary>
    /// Interfejs do zarządzania operacjami na użytkowniku w systemie.
    /// </summary>
    public interface IUserService
    {
        /// <summary>
        /// Rejestracja nowego użytkownika w systemie.
        /// </summary>
        /// <param name="UserRegisterDto user">Dane rejestracyjne nowego użytkownika.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli rejestracja przebiegła pomyślnie.</returns>
        Task<bool> RegisterUser(UserRegisterDto user);

        /// <summary>
        /// Tworzenie nowego użytkownika w bazie danych.
        /// </summary>
        /// <param name="user">Dane nowego użytkownika do utworzenia rekordu w bazie.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli użytkownik został pomyślnie utworzony.</returns>
        Task<bool> CreateUser(UserRegisterDto user);

        /// <summary>
        /// Logowanie użytkownika do systemu.
        /// </summary>
        /// <param name="user">Dane logowania użytkownika.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli logowanie przebiegło pomyślnie.</returns>
        Task<bool> LoginUser(UserLoginDto user);

        /// <summary>
        /// Dodawanie dodatkowych informacji o użytkowniku do bazy.
        /// </summary>
        /// <param name="userForm">Formularz zawierający dodatkowe informacje o użytkowniku.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli informacje o użytkowniku zostały pomyślnie dodane.</returns>
        Task<bool> AddUserDetailsForm(UserForm userForm);

        /// <summary>
        /// Generowanie ciągu tokena dla użytkownika na podstawie danych logowania.
        /// </summary>
        /// <param name="user">Dane logowania użytkownika.</param>
        /// <returns>Ciąg tokena dostępu do zasobów systemu.</returns>
        string GenerateTokenString(UserLoginDto user);

        /// <summary>
        /// Wysyłanie żądania zresetowania hasła przez użytkownika.
        /// </summary>
        /// <param name="resetPasswordReqModel">Dane dotyczące żądania zresetowania hasła.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną.</returns>
        Task<string> ResetPasswordReq(ResetPasswordReqModel resetPasswordReqModel);

        /// <summary>
        /// Resetowanie hasła użytkownika na podstawie dostarczonych danych.
        /// </summary>
        /// <param name="resetPasswordModel">Dane do zresetowania hasła użytkownika.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli hasło zostało pomyślnie zresetowane.</returns>
        Task<bool> ResetPassword(ResetPasswordModel resetPasswordModel);

        /// <summary>
        /// Pobieranie informacji o użytkowniku z menedżera użytkowników systemu.
        /// </summary>
        /// <param name="email">Adres e-mail użytkownika.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca informacje o użytkowniku lub null, jeśli użytkownik nie istnieje.</returns>
        Task<IdentityUser?> GetUserFromUserManager(string email);

        /// <summary>
        /// Pobieranie danych użytkownika na podstawie adresu e-mail.
        /// </summary>
        /// <param name="email">Adres e-mail użytkownika.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca formularz użytkownika.</returns>
        Task<UserForm> GetSignleUser(string email);

        /// <summary>
        /// Pobieranie identyfikatorów zwierząt polubionych przez użytkownika.
        /// </summary>
        /// <param name="userEmail">Adres e-mail użytkownika.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę identyfikatorów zwierząt polubionych przez użytkownika.</returns>
        Task<List<int>> GetLikedPetsByUser(string userEmail);

        /// <summary>
        /// Pobieranie listy adresów e-mail użytkowników, którzy polubili określone zwierzę.
        /// </summary>
        /// <param name="petId">Identyfikator zwierzęcia.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę adresów e-mail użytkowników, którzy polubili dane zwierzę.</returns>
        Task<List<string>> GetAllUsersWhoLikedPet(int petId);

        /// <summary>
        /// Usuwanie użytkownika z systemu na podstawie adresu e-mail.
        /// </summary>
        /// <param name="userEmail">Adres e-mail użytkownika do usunięcia.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli użytkownik został pomyślnie usunięty.</returns>
        Task<bool> DeleteUser(string userEmail);
    }

}
```

***



### ResetPasswordModel

Klasa `ResetPasswordModel` jest modelem danych, który zbiera informacje niezbędne do zresetowania hasła użytkownika.

1. **Email**
   * _Typ: string_
   * _Opis: Reprezentuje adres e-mail użytkownika, dla którego ma zostać zresetowane hasło._
2. **Token**
   * _Typ: string_
   * _Opis: Reprezentuje token używany do weryfikacji i potwierdzenia procesu resetowania hasła._
3. **NewPassword**
   * _Typ: string_
   * _Opis: Reprezentuje nowe hasło, które użytkownik chce ustawić w ramach procesu resetowania._
4. **ConfirmPassword**
   * _Typ: string_
   * _Opis: Reprezentuje potwierdzenie nowego hasła, służące do weryfikacji poprawności wprowadzonego hasła._

### ResetPasswordReqModel

Klasa `ResetPasswordReqModel` jest modelem danych, który zbiera informacje o chęci zresetowania hasła przez użytkownika

1. **Email**

* _Typ: string_
* _Opis: Reprezentuje adres e-mail użytkownika, dla którego ma zostać zresetowane hasło._

***

### UserForm

Klasa `UserForm` jest modelem danych, który zbiera informacje dotyczące potencjalnego właściciela zwierzęcia. Klasa ta reprezentuje dane dotyczące stylu życia, miejsca zamieszkania i przygotowań do posiadania zwierzęcia.

#### 1. name

* Typ: `string?`
* Opis: Reprezentuje imię potencjalnego właściciela zwierzęcia.

#### 2. lname

* Typ: `string?`
* Opis: Reprezentuje nazwisko potencjalnego właściciela zwierzęcia.

#### 3. email

* Typ: `string?`
* Opis: Reprezentuje adres e-mail potencjalnego właściciela zwierzęcia.

#### 4. phone

* Typ: `string?`
* Opis: Reprezentuje numer telefonu potencjalnego właściciela zwierzęcia.

#### 5. postCode

* Typ: `string?`
* Opis: Reprezentuje kod pocztowy miejsca zamieszkania potencjalnego właściciela zwierzęcia.

#### 6. town

* Typ: `string?`
* Opis: Reprezentuje miejscowość miejsca zamieszkania potencjalnego właściciela zwierzęcia.

#### 7. adress

* Typ: `string?`
* Opis: Reprezentuje dokładny adres miejsca zamieszkania potencjalnego właściciela zwierzęcia.

#### 8. incomeSource

* Typ: `string?`
* Opis: Reprezentuje źródło dochodu potencjalnego właściciela zwierzęcia.

#### 9. lifestyle

* Typ: `string?`
* Opis: Reprezentuje styl życia potencjalnego właściciela zwierzęcia.

#### 10. housingType

* Typ: `string?`
* Opis: Reprezentuje rodzaj mieszkania potencjalnego właściciela zwierzęcia.

#### 11. houseOwner

* Typ: `string?`
* Opis: Reprezentuje informację, czy potencjalny właściciel jest właścicielem domu.

#### 12. hoursAlone

* Typ: `string?`
* Opis: Reprezentuje ilość godzin, które zwierzę miałoby spędzać samo.

#### 13. floor

* Typ: `string?`
* Opis: Reprezentuje piętro, na którym znajduje się mieszkanie potencjalnego właściciela.

#### 14. elevator

* Typ: `string?`
* Opis: Reprezentuje informację, czy w budynku znajduje się winda.

#### 15. walksNumber

* Typ: `string?`
* Opis: Reprezentuje ilość spacerów, jakie zwierzę miałoby dostawać dziennie.

#### 16. walksTime

* Typ: `string?`
* Opis: Reprezentuje czas trwania spaceru dla zwierzęcia.

#### 17. fence

* Typ: `string?`
* Opis: Reprezentuje informację, czy w miejscu zamieszkania potencjalnego właściciela jest ogrodzenie.

#### 18. fenceHeight

* Typ: `string?`
* Opis: Reprezentuje wysokość ogrodzenia w miejscu zamieszkania potencjalnego właściciela.

#### 19. propertySize

* Typ: `string?`
* Opis: Reprezentuje rozmiar nieruchomości potencjalnego właściciela.

#### 20. petPlace

* Typ: `string?`
* Opis: Reprezentuje miejsce, gdzie zwierzę miałoby przebywać w domu.

#### 21. petPlaceAlone

* Typ: `string?`
* Opis: Reprezentuje miejsce, gdzie zwierzę miałoby przebywać samo w domu.

#### 22. careAlone

* Typ: `string?`
* Opis: Reprezentuje informację na temat opieki nad zwierzęciem, gdy jest samo w domu.

#### 23. houseMates

* Typ: `string?`
* Opis: Reprezentuje informację na temat współlokatorów potencjalnego właściciela zwierzęcia.

#### 24. animals

* Typ: `string?`
* Opis: Reprezentuje informację, czy w miejscu zamieszkania są już inne zwierzęta.

#### 25. animalsBefore

* Typ: `string?`
* Opis: Reprezentuje informację, czy potencjalny właściciel miał wcześniej zwierzęta.

#### 26. animalsBeforeText

* Typ: `string?`
* Opis: Dodatkowy tekst opisujący doświadczenia potencjalnego właściciela ze zwierzętami.

#### 27. text

* Typ: `string?`
* Opis: Dodatkowy tekst lub uwagi potencjalnego właściciela zwierzęcia.

***

### UserLoginDto

Klasa `UserLoginDto` jest modelem danych reprezentującym informacje wymagane do procesu logowania użytkownika. Służy do przechowywania adresu e-mail oraz hasła, które użytkownik wprowadza w celu uwierzytelnienia.

#### 1. EmailUser

* Typ: `string`
* Opis: Reprezentuje adres e-mail użytkownika, służący jako identyfikator podczas procesu logowania.

#### 2. PasswordUser

* Typ: `string`
* Opis: Reprezentuje hasło użytkownika, które musi zostać wprowadzone w celu pomyślnego uwierzytelnienia.

***

### UserRegisterDto

Klasa `UserRegisterDto` jest modelem danych reprezentującym informacje zbierane podczas rejestracji użytkownika. Służy do przechowywania danych takich jak imię, nazwisko, adres e-mail, hasło, potwierdzenie hasła, numer telefonu oraz akceptacja warunków użytkowania.

#### 1. Name

* Typ: `string`
* Opis: Reprezentuje imię użytkownika.

#### 2. Lname

* Typ: `string`
* Opis: Reprezentuje nazwisko użytkownika.

#### 3. Email

* Typ: `string`
* Opis: Reprezentuje adres e-mail użytkownika, służy jako unikalny identyfikator.

#### 4. Password

* Typ: `string`
* Opis: Reprezentuje hasło użytkownika.

#### 5. PasswordConfirm

* Typ: `string`
* Opis: Reprezentuje potwierdzenie hasła użytkownika, służy do weryfikacji poprawności wprowadzonego hasła.

#### 6. Phone

* Typ: `string`
* Opis: Reprezentuje numer telefonu użytkownika.

#### 7. Terms

* Typ: `bool`
* Opis: Reprezentuje akceptację warunków użytkowania. Jest `true`, gdy użytkownik zaakceptował warunki, w przeciwnym razie `false`.
