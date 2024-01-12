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
