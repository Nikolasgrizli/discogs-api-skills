# Discogs API — Database

## Release
The Release resource represents a particular physical or digital object released by one or more Artists.

### GET /releases/{release_id}{?curr_abbr}
Get a release

**Parameters:**
- `release_id` (number, required) — The Release ID _(e.g. `249504`)_
- `curr_abbr` (string, optional) — Currency for marketplace data. Defaults to the authenticated users currency. Must be one of the following: USD GBP EUR CAD AUD JPY CHF MXN BRL NZD SEK ZAR _(e.g. `USD`)_

**Example response:**
```json
{
    "title": "Never Gonna Give You Up",
    "id": 249504,
    "artists": [
        {
            "anv": "",
            "id": 72872,
            "join": "",
            "name": "Rick Astley",
            "resource_url": "https://api.discogs.com/artists/72872",
            "role": "",
            "tracks": ""
        }
    ],
    "data_quality": "Correct",
    "thumb": "https://api-img.discogs.com/kAXVhuZuh_uat5NNr50zMjN7lho=/fit-in/300x300/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/R-249504-1334592212.jpeg.jpg",
    "community": {
        "contributors": [
            {
                "resource_url": "https://api.discogs.com/users/memory",
                "username": "memory"
            },
            {
                "resource_url": "https://api.discogs.com/users/_80_",
                "username": "_80_"
            }
        ],
        "data_quality": "Correct",
        "have": 252,
        "rating": {
            "average": 3.42,
            "count": 45
        },
        "status": "Accepted",
        "submitter": {
            "resource_url": "https://api.discogs.com/users/memory",
            "username": "memory"
        },
        "want": 42
    },
    "companies": [
        {
            "catno": "",
            "entity_type": "13",
            "entity_type_name": "Phonographic Copyright (p)",
            "id": 82835,
            "name": "BMG Records (UK) Ltd.",
            "resource_url": "https://api.discogs.com/labels/82835"
        },
        {
            "catno": "",
            "entity_type": "29",
            "entity_type_name": "Mastered At",
            "id": 266218,
            "name": "Utopia Studios",
            "resource_url": "https://api.discogs.com/labels/266218"
        }
    ],
    "country": "UK",
    "date_added": "2004-04-30T08:10:05-07:00",
    "date_changed": "2012-12-03T02:50:12-07:00",
    "estimated_weight": 60,
    "extraartists": [
        {
            "anv": "Me Co",
            "id": 547352,
            "join": "",
            "name": "Me Company",
            "resource_url": "https://api.discogs.com/artists/547352",
            "role": "Design",
            "tracks": ""
        },
        {
            "anv": "Stock / Aitken / Waterman",
            "id": 20942,
            "join": "",
            "name": "Stock, Aitken & Waterman",
            "resource_url": "https://api.discogs.com/artists/20942",
            "role": "Producer, Written-By",
            "tracks": ""
        }
    ],
    "format_quantity": 1,
    "formats": [
        {
            "descriptions": [
                "7\"",
                "Single",
                "45 RPM"
            ],
            "name": "Vinyl",
            "qty": "1"
        }
    ],
    "genres": [
        "Electronic",
        "Pop"
    ],
    "identifiers": [
        {
            "type": "Barcode",
            "value": "5012394144777"
        },
    ],
    "images": [
        {
            "height": 600,
            "resource_url": "https://api-img.discogs.com/z_u8yqxvDcwVnR4tX2HLNLaQO2Y=/fit-in/600x600/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/R-249504-1334592212.jpeg.jpg",
            "type": "primary",
            "uri": "https://api-img.discogs.com/z_u8yqxvDcwVnR4tX2HLNLaQO2Y=/fit-in/600x600/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/R-249504-1334592212.jpeg.jpg",
            "uri150": "https://api-img.discogs.com/0ZYgPR4X2HdUKA_jkhPJF4SN5mM=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/R-249504-1334592212.jpeg.jpg",
            "width": 600
        },
        {
            "height": 600,
            "resource_url": "https://api-img.discogs.com/EnQXaDOs5T6YI9zq-R5I_mT7hSk=/fit-in/600x600/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/R-249504-1334592228.jpeg.jpg",
            "type": "secondary",
            "uri": "https://api-img.discogs.com/EnQXaDOs5T6YI9zq-R5I_mT7hSk=/fit-in/600x600/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/R-249504-1334592228.jpeg.jpg",
            "uri150": "https://api-img.discogs.com/abk0FWgWsRDjU4bkCDwk0gyMKBo=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/R-249504-1334592228.jpeg.jpg",
            "width": 600
        }
    ],
    "labels": [
        {
            "catno": "PB 41447",
            "entity_type": "1",
            "id": 895,
            "name": "RCA",
            "resource_url": "https://api.discogs.com/labels/895"
        }
    ],
    "lowest_price": 0.63,
    "master_id": 96559,
    "master_url": "https://api.discogs.com/masters/96559",
    "notes": "UK Release has a black label with the text \"Manufactured In England\" printed on it.\r\n\r\nSleeve:\r\n\u2117 1987 \u2022 BMG Records (UK) Ltd. \u00a9 1987 \u2022 BMG Records (UK) Ltd.\r\nDistributed in the UK by BMG Records \u2022  Distribu\u00e9 en Europe par BMG/Ariola \u2022 Vertrieb en Europa d\u00fcrch BMG/Ariola.\r\n\r\nCenter labels:\r\n\u2117 1987 Pete Waterman Ltd.\r\nOriginal Sound Recording made by PWL.\r\nBMG Records (UK) Ltd. are the exclusive licensees for the world.\r\n\r\nDurations do not appear on the release.\r\n",
    "num_for_sale": 58,
    "released": "1987",
    "released_formatted": "1987",
    "resource_url": "https://api.discogs.com/releases/249504",
    "series": [],
    "status": "Accepted",
    "styles": [
        "Synth-pop"
    ],
    "tracklist": [
        {
            "duration": "3:32",
            "position": "A",
            "title": "Never Gonna Give You Up",
            "type_": "track"
        },
        {
            "duration": "3:30",
            "position": "B",
            "title": "Never Gonna Give You Up (Instrumental)",
            "type_": "track"
        }
    ],
    "uri": "https://www.discogs.com/Rick-Astley-Never-Gonna-Give-You-Up/release/249504",
    "videos": [
        {
            "description": "Rick Astley - Never Gonna Give You Up (Extended Version)",
            "duration": 330,
            "embed": true,
            "title": "Rick Astley - Never Gonna Give You Up (Extended Version)",
            "uri": "https://www.youtube.com/watch?v=te2jJncBVG4"
        },
    ],
    "year": 1987
}
```

## Release Rating By User
The Release Rating endpoint retrieves, updates, or deletes the rating of a release for a given user.

### GET /releases/{release_id}/rating/{username}
Retrieves the release’s rating for a given user.

**Parameters:**
- `release_id` (number, required) — The Release ID _(e.g. `249504`)_
- `username` (string, required) — The username of the rating you are trying to request. _(e.g. `memory`)_

**Example response:**
```json
{
  "username": "memory",
  "release_id": 249504,
  "rating": 5
}
```

### PUT /releases/{release_id}/rating/{username}
Updates the release’s rating for a given user. Authentication as the user is required.

**Parameters:**
- `release_id` (number, required) — The Release ID _(e.g. `249504`)_
- `username` (string, required) — The username of the rating you are trying to request. _(e.g. `memory`)_
- `rating` (int, required) — The new rating for a release between 1 and 5. _(e.g. `5`)_

**Example response:**
```json
{
  "username": "memory",
  "release_id": 249504,
  "rating": 5
}
```

### DELETE /releases/{release_id}/rating/{username}
Deletes the release’s rating for a given user. Authentication as the user is required.

**Parameters:**
- `release_id` (number, required) — The Release ID _(e.g. `249504`)_
- `username` (string, required) — The username of the rating you are trying to request. _(e.g. `memory`)_

## Community Release Rating
The Community Release Rating endpoint retrieves the average rating and the total number of user ratings for a given release.

### GET /releases/{release_id}/rating
Retrieves the community release rating average and count.

**Parameters:**
- `release_id` (number, required) — The Release ID _(e.g. `249504`)_

**Example response:**
```json
{
    "rating": {
        "count": 47
        "average": 4.19
    },
    "release_id": 249504
}
```

## Release Stats
The Release Stats endpoint retrieves the total number of “haves” (in the community’s collections) and “wants” (in the community’s wantlists) for a given release.

### GET /releases/{release_id}/stats
Retrieves the release’s “have” and “want” counts.

**Parameters:**
- `release_id` (number, required) — The Release ID _(e.g. `249504`)_

**Example response:**
```json
{
  "num_have": 2315,
  "num_want": 467
}
```

## Master Release
The Master resource represents a set of similar Releases. Masters (also known as “master releases”) have a “main release” which is often the chronologically earliest.

### GET /masters/{master_id}
Get a master release

**Parameters:**
- `master_id` (number, required) — The Master ID _(e.g. `1000`)_

**Example response:**
```json
{
  "styles": [
    "Goa Trance"
  ],
  "genres": [
    "Electronic"
  ],
  "videos": [
    {
      "duration": 421,
      "description": "Electric Universe - Alien Encounter Part 2 (Spirit Zone 97)",
      "embed": true,
      "uri": "https://www.youtube.com/watch?v=n1LGinzMDi8",
      "title": "Electric Universe - Alien Encounter Part 2 (Spirit Zone 97)"
    }
  ],
  "title": "Stardiver",
  "main_release": 66785,
  "main_release_url": "https://api.discogs.com/releases/66785",
  "uri": "https://www.discogs.com/Electric-Universe-Stardiver/master/1000",
  "artists": [
    {
      "join": "",
      "name": "Electric Universe",
      "anv": "",
      "tracks": "",
      "role": "",
      "resource_url": "https://api.discogs.com/artists/21849",
      "id": 21849
    }
  ],
  "versions_url": "https://api.discogs.com/masters/1000/versions",
  "year": 1997,
  "images": [
    {
      "height": 569,
      "resource_url": "https://api-img.discogs.com/_0K5t_iLs6CzLPKTB4mwHVI3Vy0=/fit-in/600x569/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/R-66785-1213949871.jpeg.jpg",
      "type": "primary",
      "uri": "https://api-img.discogs.com/_0K5t_iLs6CzLPKTB4mwHVI3Vy0=/fit-in/600x569/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/R-66785-1213949871.jpeg.jpg",
      "uri150": "https://api-img.discogs.com/sSWjXKczZseDjX2QohG1Lc77F-w=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/R-66785-1213949871.jpeg.jpg",
      "width": 600
    },
    {
      "height": 296,
      "resource_url": "https://api-img.discogs.com/1iD31iOWgfgb2DpROI4_MvmceFw=/fit-in/600x296/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/R-66785-1213950065.jpeg.jpg",
      "type": "secondary",
      "uri": "https://api-img.discogs.com/1iD31iOWgfgb2DpROI4_MvmceFw=/fit-in/600x296/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/R-66785-1213950065.jpeg.jpg",
      "uri150": "https://api-img.discogs.com/Cm4Q_1S784pQeRfwa0lN2jsj47Y=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/R-66785-1213950065.jpeg.jpg",
      "width": 600
    }
  ],
  "resource_url": "https://api.discogs.com/masters/1000",
  "tracklist": [
    {
      "duration": "7:00",
      "position": "1",
      "type_": "track",
      "title": "Alien Encounter (Part 2)"
    },
    {
      "duration": "7:13",
      "position": "2",
      "type_": "track",
      "extraartists": [
        {
          "join": "",
          "name": "DJ Sangeet",
          "anv": "",
          "tracks": "",
          "role": "Written-By, Producer",
          "resource_url": "https://api.discogs.com/artists/25460",
          "id": 25460
        }
      ],
      "title": "From The Heart"
    },
    {
      "duration": "6:45",
      "position": "3",
      "type_": "track",
      "title": "Radio S.P.A.C.E."
    }
  ],
  "id": 1000,
  "num_for_sale": 9,
  "lowest_price": 9.36,
  "data_quality": "Correct"
}
```

## Master Release Versions

### GET /masters/{master_id}/versions{?page,per_page}
Retrieves a list of all Releases that are versions of this master. Accepts Pagination parameters.

**Parameters:**
- `master_id` (number, required) — The Master ID _(e.g. `1000`)_
- `page` (number, optional) — The page you want to request _(e.g. `3`)_
- `per_page` (number, optional) — The number of items per page _(e.g. `25`)_
- `format` (string, optional) — The format to filter _(e.g. `Vinyl`)_
- `label` (string, optional) — The label to filter _(e.g. `Scorpio Music`)_
- `released` (string, optional) — The release year to filter _(e.g. `1992`)_
- `country` (string, optional) — The country to filter _(e.g. `Belgium`)_
- `sort` (string, optional) — Sort items by this field: released (i.e. year of the release) title (i.e. title of the release) format label catno (i.e. catalog number of the release) country _(e.g. `released`)_
- `sort_order` (string, optional) — Sort items in a particular order (one of asc, desc) _(e.g. `asc`)_

**Example response:**
```json
{
  "pagination": {
    "per_page": 50,
    "items": 4,
    "page": 1,
    "urls": {},
    "pages": 1
  },
  "versions": [
    {
      "status": "Accepted",
      "stats": {
        "user": {
          "in_collection": 0,
          "in_wantlist": 0
        },
        "community": {
          "in_collection": 1067,
          "in_wantlist": 765
        }
      },
      "thumb": "https://img.discogs.com/wV56xo0Ak0M2bTCC6B_heD7Dx_o=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-18926-1381225536-8716.jpeg.jpg",
      "format": "12\", 33 ⅓ RPM",
      "country": "US",
      "title": "Plastic Dreams",
      "label": "Epic",
      "released": "1993",
      "major_formats": [
        "Vinyl"
      ],
      "catno": "49 74992",
      "resource_url": "https://api.discogs.com/releases/18926",
      "id": 18926
    },
    {
      "status": "Accepted",
      "stats": {
        "user": {
          "in_collection": 0,
          "in_wantlist": 0
        },
        "community": {
          "in_collection": 842,
          "in_wantlist": 762
        }
      },
      "thumb": "https://img.discogs.com/KAm38-Op5VlkvuJOaTGZieKwRVg=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-34228-1215760312.jpeg.jpg",
      "format": "12\", 33 ⅓ RPM",
      "country": "UK",
      "title": "Plastic Dreams (Mixes)",
      "label": "R & S Records",
      "released": "1993",
      "major_formats": [
        "Vinyl"
      ],
      "catno": "RSGB 101T",
      "resource_url": "https://api.discogs.com/releases/34228",
      "id": 34228
    },
    {
      "status": "Accepted",
      "stats": {
        "user": {
          "in_collection": 0,
          "in_wantlist": 0
        },
        "community": {
          "in_collection": 20,
          "in_wantlist": 285
        }
      },
      "thumb": "https://img.discogs.com/CnovcvhAYIle0tYTTZHo42wPz88=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb():quality(40)/discogs-images/R-1873038-1249267784.jpeg.jpg",
      "format": "12\", White Label, 33 ⅓ RPM, Promo",
      "country": "UK",
      "title": "Plastic Dreams Mixes",
      "label": "R & S Records",
      "released": "1993",
      "major_formats": [
        "Vinyl"
      ],
      "catno": "RSGB 101 T",
      "resource_url": "https://api.discogs.com/releases/1873038",
      "id": 1873038
    }
  ]
}
```

## Artist
The Artist resource represents a person in the Discogs database who contributed to a Release in some capacity.

### GET /artists/{artist_id}
Get an artist

**Parameters:**
- `artist_id` (number, required) — The Artist ID _(e.g. `108713`)_

**Example response:**
```json
{
  "namevariations": [
    "Nickleback"
  ],
  "profile": "Nickelback is a Canadian rock band from Hanna, Alberta formed in 1995. Nickelback's music is classed as hard rock and alternative metal. Nickelback is one of the most commercially successful Canadian groups, having sold almost 50 million albums worldwide, ranking as the 11th best selling music act of the 2000s, and is the 2nd best selling foreign act in the U.S. behind The Beatles for the 2000's.",
  "releases_url": "https://api.discogs.com/artists/108713/releases",
  "resource_url": "https://api.discogs.com/artists/108713",
  "uri": "https://www.discogs.com/artist/108713-Nickelback",
  "urls": [
    "http://www.nickelback.com/",
    "http://en.wikipedia.org/wiki/Nickelback"
  ],
  "data_quality": "Needs Vote",
  "id": 108713,
  "images": [
    {
      "height": 260,
      "resource_url": "https://api-img.discogs.com/9xJ5T7IBn23DDMpg1USsDJ7IGm4=/330x260/smart/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/A-108713-1110576087.jpg.jpg",
      "type": "primary",
      "uri": "https://api-img.discogs.com/9xJ5T7IBn23DDMpg1USsDJ7IGm4=/330x260/smart/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/A-108713-1110576087.jpg.jpg",
      "uri150": "https://api-img.discogs.com/--xqi8cBtaBZz3qOjVcvzGvNRmU=/150x150/smart/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/A-108713-1110576087.jpg.jpg",
      "width": 330
    },
    {
      "height": 500,
      "resource_url": "https://api-img.discogs.com/r1jRG8b9-nlqTHPlJ-t8JR5ugoA=/493x500/smart/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/A-108713-1264273865.jpeg.jpg",
      "type": "secondary",
      "uri": "https://api-img.discogs.com/r1jRG8b9-nlqTHPlJ-t8JR5ugoA=/493x500/smart/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/A-108713-1264273865.jpeg.jpg",
      "uri150": "https://api-img.discogs.com/6K-cI5xDgsurmc-2OX6uCygzDgw=/150x150/smart/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/A-108713-1264273865.jpeg.jpg",
      "width": 493
    }
  ],
  "members": [
    {
      "active": true,
      "id": 270222,
      "name": "Chad Kroeger",
      "resource_url": "https://api.discogs.com/artists/270222"
    },
    {
      "active": true,
      "id": 685755,
      "name": "Daniel Adair",
      "resource_url": "https://api.discogs.com/artists/685755"
    },
    {
      "active": true,
      "id": 685754,
      "name": "Mike Kroeger",
      "resource_url": "https://api.discogs.com/artists/685754"
    },
    {
      "active": true,
      "id": 685756,
      "name": "Ryan \"Vik\" Vikedal",
      "resource_url": "https://api.discogs.com/artists/685756"
    },
    {
      "active": true,
      "id": 685757,
      "name": "Ryan Peake",
      "resource_url": "https://api.discogs.com/artists/685757"
    }
  ],
}
```

## Artist Releases
Returns a list of Releases and Masters associated with the Artist. Accepts Pagination.

### GET /artists/{artist_id}/releases{?sort,sort_order}
Get an artist’s releases

**Parameters:**
- `artist_id` (number, required) — The Artist ID _(e.g. `108713`)_
- `sort` (string, optional) — Sort items by this field: year (i.e. year of the release) title (i.e. title of the release) format _(e.g. `year`)_
- `sort_order` (string, optional) — Sort items in a particular order (one of asc, desc) _(e.g. `asc`)_

**Example response:**
```json
{
  "pagination": {
    "per_page": 50,
    "items": 9,
    "page": 1,
    "urls": {},
    "pages": 1
  },
  "releases": [
    {
      "artist": "Nickelback",
      "id": 173765,
      "main_release": 3128432,
      "resource_url": "http://api.discogs.com/masters/173765",
      "role": "Main",
      "thumb": "https://api-img.discogs.com/lb0zp7--FLaRP0LmJ4W6DhfweNc=/fit-in/90x90/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/R-5557864-1396493975-7618.jpeg.jpg",
      "title": "Curb",
      "type": "master",
      "year": 1996
    },
    {
      "artist": "Nickelback",
      "format": "CD, EP",
      "id": 4299404,
      "label": "Not On Label (Nickelback Self-released)",
      "resource_url": "http://api.discogs.com/releases/4299404",
      "role": "Main",
      "status": "Accepted",
      "thumb": "https://api-img.discogs.com/eFRGD78N7UhtvRjhdLZYXs2QJXk=/fit-in/90x90/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/R-4299404-1361106117-3632.jpeg.jpg",
      "title": "Hesher",
      "type": "release",
      "year": 1996
    },
    {
      "artist": "Nickelback",
      "id": 173767,
      "main_release": 1905922,
      "resource_url": "http://api.discogs.com/masters/173767",
      "role": "Main",
      "thumb": "https://api-img.discogs.com/12LXbUV44IHjyb6drFZOTQxgCqs=/fit-in/90x90/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/R-1905922-1251540516.jpeg.jpg",
      "title": "Leader Of Men",
      "type": "master",
      "year": 1999
    }
  ]
}
```

## Label
The Label resource represents a label, company, recording studio, location, or other entity involved with Artists and Releases. Labels were recently expanded in scope to include things that aren’t labels – the name is an artifact of this history.

### GET /labels/{label_id}
Get a label

**Parameters:**
- `label_id` (number, required) — The Label ID _(e.g. `1`)_

**Example response:**
```json
{
  "profile": "Classic Techno label from Detroit, USA.\r\n[b]Label owner:[/b] [a=Carl Craig].\r\n",
  "releases_url": "https://api.discogs.com/labels/1/releases",
  "name": "Planet E",
  "contact_info": "Planet E Communications\r\nP.O. Box 27218\r\nDetroit, 48227, USA\r\n\r\np: 313.874.8729 \r\nf: 313.874.8732\r\n\r\nemail: info AT Planet-e DOT net\r\n",
  "uri": "https://www.discogs.com/label/1-Planet-E",
  "sublabels": [
    {
      "resource_url": "https://api.discogs.com/labels/86537",
      "id": 86537,
      "name": "Antidote (4)"
    },
    {
      "resource_url": "https://api.discogs.com/labels/41841",
      "id": 41841,
      "name": "Community Projects"
    }
  ],
  "urls": [
    "http://www.planet-e.net",
    "http://planetecommunications.bandcamp.com",
    "http://twitter.com/planetedetroit"
  ],
  "images": [
    {
      "height": 24,
      "resource_url": "https://api-img.discogs.com/85-gKw4oEXfDp9iHtqtCF5Y_ZgI=/fit-in/132x24/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/L-1-1111053865.png.jpg",
      "type": "primary",
      "uri": "https://api-img.discogs.com/85-gKw4oEXfDp9iHtqtCF5Y_ZgI=/fit-in/132x24/filters:strip_icc():format(jpeg):mode_rgb():quality(96)/discogs-images/L-1-1111053865.png.jpg",
      "uri150": "https://api-img.discogs.com/cYmCut4Yh99FaLFHyoqkFo-Md1E=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/L-1-1111053865.png.jpg",
      "width": 132
    }
  ],
  "resource_url": "https://api.discogs.com/labels/1",
  "id": 1,
  "data_quality": "Needs Vote"
}
```

## All Label Releases

### GET /labels/{label_id}/releases{?page,per_page}
Returns a list of Releases associated with the label. Accepts Pagination parameters.

**Parameters:**
- `label_id` (number, required) — The Label ID _(e.g. `1`)_
- `page` (number, optional) — The page you want to request _(e.g. `3`)_
- `per_page` (number, optional) — The number of items per page _(e.g. `25`)_

**Example response:**
```json
{
  "pagination": {
    "per_page": 5,
    "pages": 68,
    "page": 1,
    "urls": {
      "last": "https://api.discogs.com/labels/1/releases?per_page=5&page=68",
      "next": "https://api.discogs.com/labels/1/releases?per_page=5&page=2"
    },
    "items": 338
  },
  "releases": [
    {
      "artist": "Andrea Parker",
      "catno": "!K7071CD",
      "format": "CD, Mixed",
      "id": 2801,
      "resource_url": "http://api.discogs.com/releases/2801",
      "status": "Accepted",
      "thumb": "https://api-img.discogs.com/cYmCut4Yh99FaLFHyoqkFo-Md1E=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/L-1-1111053865.png.jpg",
      "title": "DJ-Kicks",
      "year": 1998
    },
    {
      "artist": "Naomi Daniel",
      "catno": "2INZ 00140",
      "format": "12\"",
      "id": 65040,
      "resource_url": "http://api.discogs.com/releases/65040",
      "status": "Accepted",
      "thumb": "https://api-img.discogs.com/cYmCut4Yh99FaLFHyoqkFo-Md1E=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/L-1-1111053865.png.jpg",
      "title": "Stars",
      "year": 1993
    },
    {
      "artist": "Innerzone Orchestra",
      "catno": "546 137-2",
      "format": "CD, Album, P/Mixed",
      "id": 9922,
      "resource_url": "http://api.discogs.com/releases/9922",
      "status": "Accepted",
      "thumb": "https://api-img.discogs.com/cYmCut4Yh99FaLFHyoqkFo-Md1E=/fit-in/150x150/filters:strip_icc():format(jpeg):mode_rgb()/discogs-images/L-1-1111053865.png.jpg",
      "title": "Programmed",
      "year": 1999
    }
  ]
}
```

## Search
Issue a search query to our database. This endpoint accepts pagination parameters
Authentication (as any user) is required.

### GET /database/search?q={query}&{?type,title,release_title,credit,artist,anv,label,genre,style,country,year,format,catno,barcode,track,submitter,contributor}
Issue a search query

**Parameters:**
- `query` (string, optional) — Your search query _(e.g. `nirvana`)_
- `type` (string, optional) — String. One of release, master, artist, label _(e.g. `release`)_
- `title` (string, optional) — Search by combined “Artist Name - Release Title” title field. _(e.g. `nirvana - nevermind`)_
- `release_title` (string, optional) — Search release titles. _(e.g. `nevermind`)_
- `credit` (string, optional) — Search release credits. _(e.g. `kurt`)_
- `artist` (string, optional) — Search artist names. _(e.g. `nirvana`)_
- `anv` (string, optional) — Search artist ANV. _(e.g. `nirvana`)_
- `label` (string, optional) — Search label names. _(e.g. `dgc`)_
- `genre` (string, optional) — Search genres. _(e.g. `rock`)_
- `style` (string, optional) — Search styles. _(e.g. `grunge`)_
- `country` (string, optional) — Search release country. _(e.g. `canada`)_
- `year` (string, optional) — Search release year. _(e.g. `1991`)_
- `format` (string, optional) — Search formats. _(e.g. `album`)_
- `catno` (string, optional) — Search catalog number. _(e.g. `DGCD-24425`)_
- `barcode` (string, optional) — Search barcodes. _(e.g. `7 2064-24425-2 4`)_
- `track` (string, optional) — Search track titles. _(e.g. `smells like teen spirit`)_
- `submitter` (string, optional) — Search submitter username. _(e.g. `milKt`)_
- `contributor` (string, optional) — Search contributor usernames. _(e.g. `jerome99`)_

**Example request:**
```http
GET https://api.discogs.com/database/search?release_title=nevermind&artist=nirvana&per_page=3&page=1
```

## Videos
If your application integrates YouTube videos, then third party cookies may be used. You can view YouTube and Google’s cookie policy here.
