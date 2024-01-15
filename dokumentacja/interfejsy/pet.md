# Pet

```csharp
namespace shelter.Interfaces.Pet
{
    /// <summary>
    /// Interfejs do zarządzania operacjami związanymi ze zwierzętami.
    /// </summary>
    public interface IPetService
    {
        /// <summary>
        /// Dodaje nowy formularz dotyczący zwierzaka do bazy danych .
        /// </summary>
        /// <param name="PetForm pet">Formularz zwierzęcia do dodania.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli formularz zwierzęcia został pomyślnie dodany.</returns>
        Task<bool> AddPetForm(PetForm pet);

        /// <summary>
        /// Aktualizuje informacje o istniejącym zwierzęciu.
        /// </summary>
        /// <param name="PetForm pet">Zaktualizowane informacje o zwierzęciu.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli informacje o zwierzęciu zostały pomyślnie zaktualizowane.</returns>
        Task<bool> UpdatePet(PetForm pet);

        /// <summary>
        /// Usuwa zwierzę na podstawie podanego identyfikatora.
        /// </summary>
        /// <param name="id">Identyfikator zwierzęcia do usunięcia.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli zwierzę zostało pomyślnie usunięte.</returns>
        Task<bool> DeletePet(int id);

        /// <summary>
        /// Pobiera listę wszystkich zwierząt w schronisku.
        /// </summary>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę zwierząt należących do schroniska.</returns>
        Task<List<PetsBelongsToShelterDto>> GetAllPets();

        /// <summary>
        /// Pobiera listę wszystkich psów w schronisku.
        /// </summary>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę psów należących do schroniska.</returns>
        Task<List<PetsBelongsToShelterDto>> GetAllDogs();

        /// <summary>
        /// Pobiera listę wszystkich kotów w schronisku.
        /// </summary>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę kotów należących do schroniska.</returns>
        Task<List<PetsBelongsToShelterDto>> GetAllCats();

        /// <summary>
        /// Pobiera listę wszystkich gryzoni w schronisku.
        /// </summary>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę gryzoni należących do schroniska.</returns>
        Task<List<PetsBelongsToShelterDto>> GetAllRodents();

        /// <summary>
        /// Pobiera listę wszystkich innych zwierząt (nie psów, kotów ani gryzoni) w schronisku.
        /// </summary>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca listę innych zwierząt należących do schroniska.</returns>
        Task<List<PetsBelongsToShelterDto>> GetAllOtherPets();

        /// <summary>
        /// Pobiera szczegółowe informacje o określonym zwierzęciu na podstawie podanego identyfikatora.
        /// </summary>
        /// <param name=" int id">Identyfikator zwierzęcia do pobrania informacji.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca szczegółowe informacje o określonym zwierzęciu.</returns>
        Task<PetByIdDto> GetPetById(int id);

        /// <summary>
        /// Dodaje zwierzę do listy polubionych zwierząt użytkownika.
        /// </summary>
        /// <param name="likedPetListModel">Model zawierający informacje o polubionym zwierzęciu i użytkowniku.</param>
        /// <returns>Zadanie reprezentujące operację asynchroniczną. Zwraca true, jeśli zwierzę zostało pomyślnie dodane do listy polubionych zwierząt.</returns>
        Task<bool> AddLikedPetList(LikedPetListModel likedPetListModel);
    }

}
```

***



### LikedPetListModel

Klasa `LikedPetListModel` jest modelem danych używanym do przechowywania informacji dotyczących zwierząt, które zostały polubione przez użytkownika. Służy do gromadzenia adresu e-mail użytkownika, oraz  przypisanych do tego emaila, listy identyfikatorów zwierząt, które uzyskały jego polubienie.

#### 1. userEmail

* Typ: `string`
* Opis: Reprezentuje adres e-mail użytkownika, który polubił zwierzęta.

#### 2. likedPetIds

* Typ: `List<int>`
* Opis: Reprezentuje listę identyfikatorów zwierząt, które zostały polubione przez użytkownika. Każdy identyfikator jest liczbą całkowitą.

***



### PetForm

Klasa `PetForm` jest modelem danych reprezentującym informacje związane z zwierzakiem. Stworzona jest przedewszystkim do przechowywania szczegółów dotyczących zwierząt, takich jak ich identyfikator, imię, rodzaj, płeć oraz różne inne atrybuty.&#x20;

#### 1. Id

* Typ: `int?`
* Opis: Reprezentuje unikalny identyfikator zwierzęcia.

#### 2. Name

* Typ: `string?`
* Opis: Reprezentuje imię zwierzęcia.

#### 3. Images

* Typ: `List<string>?`
* Opis: Reprezentuje obrazów w postaci String Base64 związanych ze zwierzęciem. Jest oznaczone adnotacją `[FromForm(Name = "images[]")]` w celu poprawnego przypisania modelu z formularza.

#### 4. Type

* Typ: `string?`
* Opis: Reprezentuje rodzaj lub gatunek zwierzęcia (np. pies, kot).

#### 5. Gender

* Typ: `string?`
* Opis: Reprezentuje płeć zwierzęcia.

#### 6. Castration

* Typ: `string?`
* Opis: Reprezentuje status kastracji zwierzęcia.

#### 7. Breed

* Typ: `string?`
* Opis: Reprezentuje rasę lub mieszankę ras zwierzęcia.

#### 8. Size

* Typ: `string?`
* Opis: Reprezentuje kategorię rozmiaru zwierzęcia (np. mały, średni, duży).

#### 9. Age

* Typ: `string?`
* Opis: Reprezentuje wiek lub zakres wieku zwierzęcia.

#### 10. Vaccination

* Typ: `string?`
* Opis: Reprezentuje status szczepień zwierzęcia.

#### 11. ChildFriendly

* Typ: `string?`
* Opis: Reprezentuje przyjazność dla dzieci zwierzęcia.

#### 12. BasicTraining

* Typ: `string?`
* Opis: Reprezentuje poziom wyszkolenia zwierzaka

#### 13. Activity

* Typ: `string?`
* Opis: Reprezentuje poziom aktywności zwierzęcia.

#### 14. OtherDogs

* Typ: `string?`
* Opis: Reprezentuje informacje czy w pobliżu znajdują się inne psy

#### 15. OtherCats

* Typ: `string?`
* Opis: Reprezentuje informacje czy w pobliżu znajdują się inne koty

#### 16. Cuddly

* Typ: `string?`
* Opis: Reprezentuje skłonność do przytulania się lub uczucie miłości zwierzęcia.

#### 17. Temper

* Typ: `string?`
* Opis: Reprezentuje ogólny temperament zwierzęcia.

#### 18. Text

* Typ: `string?`
* Opis: Dodatkowy tekst lub opis związany ze zwierzęciem.

#### 19. ShelterEmail

* Typ: `string?`
* Opis: Reprezentuje adres e-mail schroniska lub organizacji zarządzającej zwierzęciem.
