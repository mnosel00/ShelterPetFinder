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
