# User

```csharp
 public interface IUserService
 {
     Task<bool> RegisterUser(UserRegisterDto user);
     Task<bool> CreateUser(UserRegisterDto user);
     Task<bool> LoginUser(UserLoginDto user);
     Task<bool> AddUserDetailsForm(UserForm userForm);
     string GenerateTokenString(UserLoginDto user);
     Task<string> ResetPasswordReq(ResetPasswordReqModel resetPasswordReqModel);
     Task<bool> ResetPassword(ResetPasswordModel resetPasswordModel);
     Task<IdentityUser?> GetUserFromUserManager(string email);
     Task<UserForm> GetSignleUser (string email);
     Task<List<int>> GetLikedPetsByUser(string userEmail);
     Task<List<string>> GetAllUsersWhoLikedPet(int petId);
     Task<bool> DeleteUser (string userEmail);
 }
```
