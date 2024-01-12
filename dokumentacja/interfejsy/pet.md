# Pet

```apex
public interface IPetService
{
    Task<bool> AddPetForm(PetForm pet);
    Task<bool> UpdatePet(PetForm pet);
    Task <bool> DeletePet(int id);
    Task<List<PetsBelongsToShelterDto>> GetAllPets();
    Task<List<PetsBelongsToShelterDto>> GetAllDogs();
    Task<List<PetsBelongsToShelterDto>> GetAllCats();
    Task<List<PetsBelongsToShelterDto>> GetAllRodents();
    Task<List<PetsBelongsToShelterDto>> GetAllOtherPets();
    Task<PetByIdDto> GetPetById(int id);
    Task<bool> AddLikedPetList(LikedPetListModel likedPetListModel);
}
```
