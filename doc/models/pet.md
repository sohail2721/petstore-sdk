
# Pet

## Structure

`Pet`

## Fields

| Name | Type | Tags | Description | Getter | Setter |
|  --- | --- | --- | --- | --- | --- |
| `id` | `?int` | Optional | - | getId(): ?int | setId(?int id): void |
| `name` | `string` | Required | - | getName(): string | setName(string name): void |
| `category` | [`?Category`](../../doc/models/category.md) | Optional | - | getCategory(): ?Category | setCategory(?Category category): void |
| `photoUrls` | `string[]` | Required | - | getPhotoUrls(): array | setPhotoUrls(array photoUrls): void |
| `tags` | [`?(Tag[])`](../../doc/models/tag.md) | Optional | - | getTags(): ?array | setTags(?array tags): void |
| `status` | [`?string(PetStatusEnum)`](../../doc/models/pet-status-enum.md) | Optional | pet status in the store | getStatus(): ?string | setStatus(?string status): void |

## Example (as JSON)

```json
{
  "id": 120,
  "name": "name0",
  "category": {
    "id": 232,
    "name": "name2"
  },
  "photoUrls": [
    "photoUrls5",
    "photoUrls6"
  ],
  "tags": [
    {
      "id": 26,
      "name": "name0"
    }
  ],
  "status": "available"
}
```

