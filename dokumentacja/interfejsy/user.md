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
