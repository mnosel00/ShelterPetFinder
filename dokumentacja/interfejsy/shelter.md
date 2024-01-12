# Shelter

```csharp
public interface IShelterService
{
    Task<ShelterLoginDto> CreateAccount(string email);
    Task<bool> CreateUserShelter(string email);
    string GenerateTokenString(ShelterLoginDto shelter);
    Task<bool> LoginUser(ShelterLoginDto shelter);
    Task<bool> AddShelterDetailsForm(ShelterForm shelterForm);
    Task<List<PetsBelongsToShelterDto>> GetAllPetsBelongsToShelter(string shelterEmail);
    Task<List<PetsBelongsToShelterDto>> GetAllDogsBelongsToShelter(string shelterEmail);
    Task<List<PetsBelongsToShelterDto>> GetAllCatsBelongsToShelter(string shelterEmail);
    Task<List<PetsBelongsToShelterDto>> GetAllRodentsBelongsToShelter(string shelterEmail);
    Task<List<PetsBelongsToShelterDto>> GetOthersBelongsToShelter(string shelterEmail);
    Task<ShelterForm> GetSingleShelter ( string shelterEmail);
    Task<string> ResetPassworReq(ResetPasswordReqModel resetPasswordReqModel);
    Task<bool> ResetPassword(ResetPasswordModel resetPasswordModel);
   
}
```
