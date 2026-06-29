# Discogs API — User Collection

## Collection
The Collection resource allows you to view and manage a user’s collection. A collection is arranged into folders. Every user has two permanent folders already:
ID 0, the “All” folder, which cannot have releases added to it, and ID 1, the “Uncategorized” folder.
Because it’s possible to own more than one copy of a release, each with its own notes, grading, and so on, each instance of a release in a folder has an instance ID.
Through the Discogs website, users can create custom notes fields. There is not yet an API method for creating and deleting these fields, but they can be listed, and the values of the fields on any instance can be modified.

### GET /users/{username}/collection/folders
Retrieve a list of folders in a user’s collection. If the collection has been made private by its owner, authentication as the collection owner is required. If you are not authenticated as the collection owner, only folder ID 0 (the “All” folder) will be visible (if the requested user’s collection is public).

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to retrieve. _(e.g. `rodneyfool`)_

**Example response:**
```json
{
  "folders": [
    {
      "id": 0,
      "count": 23,
      "name": "All",
      "resource_url": "https://api.discogs.com/users/example/collection/folders/0"
    },
    {
      "id": 1,
      "count": 20,
      "name": "Uncategorized",
      "resource_url": "https://api.discogs.com/users/example/collection/folders/1"
    }
  ]
}
```

### POST /users/{username}/collection/folders
Create a new folder in a user’s collection. Authentication as the collection owner is required.

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to retrieve. _(e.g. `rodneyfool`)_
- `name` (string, optional) — The name of the newly-created folder. _(e.g. `My favorites`)_

**Example response:**
```json
{
  "id": 232842,
  "name": "My Music",
  "count": 0,
  "resource_url": "https://api.discogs.com/users/example/collection/folders/232842"
}
```

## Collection Folder

### GET /users/{username}/collection/folders/{folder_id}
Retrieve metadata about a folder in a user’s collection. If folder_id is not 0, authentication as the collection owner is required.

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to request. _(e.g. `rodneyfool`)_
- `folder_id` (number, required) — The ID of the folder to request. _(e.g. `3`)_

**Example response:**
```json
{
  "id": 1,
  "count": 20,
  "name": "Uncategorized",
  "resource_url": "https://api.discogs.com/users/example/collection/folders/1"
}
```

### POST /users/{username}/collection/folders/{folder_id}
Edit a folder’s metadata. Folders 0 and 1 cannot be renamed. Authentication as the collection owner is required.

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to modify. _(e.g. `rodneyfool`)_
- `folder_id` (number, required) — The ID of the folder to modify. _(e.g. `3`)_

**Example response:**
```json
{
  "id": 392,
  "count": 3,
  "name": "An Example Folder",
  "resource_url": "https://api.discogs.com/users/example/collection/folders/392"
}
```

### DELETE /users/{username}/collection/folders/{folder_id}
Delete a folder from a user’s collection. A folder must be empty before it can be deleted. Authentication as the collection owner is required.

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to modify. _(e.g. `rodneyfool`)_
- `folder_id` (number, required) — The ID of the folder to delete. _(e.g. `3`)_

## Collection Items By Release

### GET /users/{username}/collection/releases/{release_id}
View the user’s collection folders which contain a specified release. This will also show information about each release instance. The release_id must be non-zero. Authentication as the collection owner is required if the owner’s collection is private.

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to view. _(e.g. `susan.salkeld`)_
- `release_id` (number, required) — The ID of the release to request. _(e.g. `7781525`)_

**Example response:**
```json
{
  "pagination": {
    "per_page": 50,
    "items": 28,
    "page": 1,
    "urls": {},
    "pages": 1
  },
  "releases": [
    {
      "instance_id": 148842233,
      "rating": 4,
      "basic_information": {
        "labels": [
          {
            "name": "Varèse Vintage",
            "entity_type": "1",
            "catno": "302 067 361 1",
            "resource_url": "http://api.discogs.com/labels/151979",
            "id": 151979,
            "entity_type_name": "Label"
          }
        ],
        "formats": [
          {
            "descriptions": [
              "LP",
              "Album",
              "Compilation",
              "Limited Edition",
              "Mono"
            ],
            "name": "Vinyl",
            "qty": "2"
          }
        ],
        "thumb": "http://api-img.discogs.com/FGmDbZ6M9wNPwEAsn0yWz1jzQuI=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb():quality(90)/discogs-images/R-7781525-1449187274-5587.jpeg.jpg",
        "title": "The BBC Radio Sessions",
        "artists": [
          {
            "join": ",",
            "name": "The Zombies",
            "anv": "",
            "tracks": "",
            "role": "",
            "resource_url": "http://api.discogs.com/artists/262221",
            "id": 262221
          }
        ],
        "resource_url": "http://api.discogs.com/releases/7781525",
        "year": 2015,
        "id": 7781525
      },
      "folder_id": 688739,
      "date_added": "2015-11-30T10:54:13-08:00",
      "id": 7781525
    },
    {
      "instance_id": 181301430,
      "rating": 4,
      "basic_information": {
        "labels": [
          {
            "name": "Varèse Vintage",
            "entity_type": "1",
            "catno": "302 067 361 1",
            "resource_url": "http://api.discogs.com/labels/151979",
            "id": 151979,
            "entity_type_name": "Label"
          }
        ],
        "formats": [
          {
            "descriptions": [
              "LP",
              "Album",
              "Compilation",
              "Limited Edition",
              "Mono"
            ],
            "name": "Vinyl",
            "qty": "2"
          }
        ],
        "thumb": "http://api-img.discogs.com/FGmDbZ6M9wNPwEAsn0yWz1jzQuI=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb():quality(90)/discogs-images/R-7781525-1449187274-5587.jpeg.jpg",
        "title": "The BBC Radio Sessions",
        "artists": [
          {
            "join": ",",
            "name": "The Zombies",
            "anv": "",
            "tracks": "",
            "role": "",
            "resource_url": "http://api.discogs.com/artists/262221",
            "id": 262221
          }
        ],
        "resource_url": "http://api.discogs.com/releases/7781525",
        "year": 2015,
        "id": 7781525
      },
      "folder_id": 1,
      "date_added": "2016-07-27T08:11:29-07:00",
      "id": 7781525
    },
    {
      "instance_id": 181301442,
      "rating": 4,
      "basic_information": {
        "labels": [
          {
            "name": "Varèse Vintage",
            "entity_type": "1",
            "catno": "302 067 361 1",
            "resource_url": "http://api.discogs.com/labels/151979",
            "id": 151979,
            "entity_type_name": "Label"
          }
        ],
        "formats": [
          {
            "descriptions": [
              "LP",
              "Album",
              "Compilation",
              "Limited Edition",
              "Mono"
            ],
            "name": "Vinyl",
            "qty": "2"
          }
        ],
        "thumb": "http://api-img.discogs.com/FGmDbZ6M9wNPwEAsn0yWz1jzQuI=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb():quality(90)/discogs-images/R-7781525-1449187274-5587.jpeg.jpg",
        "title": "The BBC Radio Sessions",
        "artists": [
          {
            "join": ",",
            "name": "The Zombies",
            "anv": "",
            "tracks": "",
            "role": "",
            "resource_url": "http://api.discogs.com/artists/262221",
            "id": 262221
          }
        ],
        "resource_url": "http://api.discogs.com/releases/7781525",
        "year": 2015,
        "id": 7781525
      },
      "folder_id": 688739,
      "date_added": "2016-07-27T08:11:35-07:00",
      "id": 7781525
    }
  ]
}
```

## Collection Items By Folder

### GET /users/{username}/collection/folders/{folder_id}/releases
Returns the list of item in a folder in a user’s collection. Accepts Pagination parameters. Basic information about each release is provided, suitable for display in a list. For detailed information, make another API call to fetch the corresponding release. If folder_id is not 0, or the collection has been made private by its owner, authentication as the collection owner is required. If you are not authenticated as the collection owner, only public notes fields will be visible. Valid sort keys are: label artist title catno format rating added year

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to request. _(e.g. `rodneyfool`)_
- `folder_id` (number, required) — The ID of the folder to request. _(e.g. `3`)_
- `sort` (string, optional) — Sort items by this field (see below for all valid sort keys. _(e.g. `artist`)_
- `sort_order` (string, optional) — Sort items in a particular order (asc or desc) _(e.g. `desc`)_

**Example response:**
```json
{
  "pagination": {
    "per_page": 1,
    "pages": 14,
    "page": 1,
    "items": 14,
    "urls": {
      "next": "https://api.discogs.com/users/example/collection/folders/1/releases?page=2&per_page=1",
      "last": "https://api.discogs.com/users/example/collection/folders/1/releases?page=2&per_page=14",
    }
  },
  "releases": [
    {
      "id": 2464521,
      "instance_id": 1,
      "folder_id": 1,
      "rating": 0,
      "basic_information": {
        "id": 2464521,
        "title": "Information Chase",
        "year": 2006,
        "resource_url": "https://api.discogs.com/releases/2464521",
        "thumb": "https://api-img.discogs.com/vzpYq4_kc52GZFs14c0SCJ0ZE84=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/R-2464521-1285519861.jpeg.jpg",
        "cover_image": "https://api-img.discogs.com/vzpYq4_kc52GZFs14c0SCJ0ZE84/fit-in/500x500/filters:strip_icc():format(jpeg):mode_rgb():quality(90)/discogs-images/R-2464521-1285519861.jpeg.jpg",
        "formats": [
          {
            "qty": "1",
            "descriptions": [ "Mini", "EP" ],
            "name": "CDr"
          }
        ],
        "labels": [
          {
            "resource_url": "https://api.discogs.com/labels/11647",
            "entity_type": "",
            "catno": "8BP059",
            "id": 11647,
            "name": "8bitpeoples"
          }
        ],
        "artists": [
          {
            "id": 103906,
            "name": "Bit Shifter",
            "join": "",
            "resource_url": "https://api.discogs.com/artists/103906",
            "anv": "",
            "tracks": "",
            "role": ""
          }
        ],
        "genres": [
            "Electronic", 
            "Pop"
        ],
        "styles": [
            "Chiptune"
        ]
      },
      "notes": [
        {
          "field_id": 3,
          "value": "bleep bloop blorp."
        }
      ]
    }
  ]
}
```

## Add To Collection Folder

### POST /users/{username}/collection/folders/{folder_id}/releases/{release_id}
Add a release to a folder in a user’s collection. The folder_id must be non-zero – you can use 1 for “Uncategorized”. Authentication as the collection owner is required.

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to modify. _(e.g. `rodneyfool`)_
- `folder_id` (number, required) — The ID of the folder to modify. _(e.g. `3`)_
- `release_id` (number, required) — The ID of the release you are adding. _(e.g. `130076`)_

**Example response:**
```json
{
  "instance_id": 3,
  "resource_url": "https://api.discogs.com/users/example/collection/folders/1/release/1/instance/3"
}
```

## Change Rating Of Release

### POST /users/{username}/collection/folders/{folder_id}/releases/{release_id}/instances/{instance_id}
Change the rating on a release and/or move the instance to another folder. This endpoint potentially takes 2 folder_id parameters: one in the URL (which is the folder you are requesting, and is required), and one in the request body (representing the folder you want to move the instance to, which is optional) Authentication as the collection owner is required.

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to modify. _(e.g. `rodneyfool`)_
- `folder_id` (number, optional) — The ID of the folder to modify (this parameter is set in the request body and is set if you want to move the instance to this folder). _(e.g. `4`)_
- `release_id` (number, required) — The ID of the release you are modifying. _(e.g. `130076`)_
- `instance_id` (number, required) — The ID of the instance. _(e.g. `1`)_
- `rating` (number, optional) — The rating of the instance you are supplying. _(e.g. `5`)_

## Delete Instance From Folder

### DELETE /users/{username}/collection/folders/{folder_id}/releases/{release_id}/instances/{instance_id}
Remove an instance of a release from a user’s collection folder. To move the release to the “Uncategorized” folder instead, use the POST method. Authentication as the collection owner is required.

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to modify. _(e.g. `rodneyfool`)_
- `folder_id` (number, required) — The ID of the folder to modify. _(e.g. `3`)_
- `release_id` (number, required) — The ID of the release you are modifying. _(e.g. `130076`)_
- `instance_id` (number, required) — The ID of the instance. _(e.g. `1`)_

**Example response:**
```json
{
  "message": "You don't have permission to access this resource."
}
```

## List Custom Fields

### GET /users/{username}/collection/fields
Retrieve a list of user-defined collection notes fields. These fields are available on every release in the collection. If the collection has been made private by its owner, authentication as the collection owner is required. If you are not authenticated as the collection owner, only fields with public set to true will be visible.

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to modify. _(e.g. `rodneyfool`)_

**Example response:**
```json
{
  "fields": [
    {
      "name": "Media",
      "options": [
        "Mint (M)",
        "Near Mint (NM or M-)",
        "Very Good Plus (VG+)",
        "Very Good (VG)",
        "Good Plus (G+)",
        "Good (G)",
        "Fair (F)",
        "Poor (P)"
      ],
      "id": 1,
      "position": 1,
      "type": "dropdown",
      "public": true
    },
    {
      "name": "Sleeve",
      "options": [
        "Generic",
        "No Cover",
        "Mint (M)",
        "Near Mint (NM or M-)",
        "Very Good Plus (VG+)",
        "Very Good (VG)",
        "Good Plus (G+)",
        "Good (G)",
        "Fair (F)",
        "Poor (P)"
      ],
      "id": 2,
      "position": 2,
      "type": "dropdown",
      "public": true
    },
    {
      "name": "Notes",
      "lines": 3,
      "id": 3,
      "position": 3,
      "type": "textarea",
      "public": true
    }
  ]
}
```

## Edit Fields Instance

### POST /users/{username}/collection/folders/{folder_id}/releases/{release_id}/instances/{instance_id}/fields/{field_id}{?value}
Change the value of a notes field on a particular instance.

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to modify. _(e.g. `rodneyfool`)_
- `value` (string, required) — The new value of the field. If the field’s type is dropdown, the value must match one of the values in the field’s list of options. _(e.g. `foo`)_
- `folder_id` (number, required) — The ID of the folder to modify. _(e.g. `3`)_
- `release_id` (number, required) — The ID of the release you are modifying. _(e.g. `130076`)_
- `instance_id` (number, required) — The ID of the instance. _(e.g. `1`)_
- `field_id` (number, required) — The ID of the field. _(e.g. `8`)_

## Collection Value

### GET /users/{username}/collection/value
Returns the minimum, median, and maximum value of a user’s collection. Authentication as the collection owner is required.

**Parameters:**
- `username` (string, required) — The username of the collection you are trying to modify. _(e.g. `rodneyfool`)_

**Example response:**
```json
{
  "maximum": "$250.00",
  "median": "$100.25",
  "minimum": "$75.50"
}
```
