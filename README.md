# Epicentre Publishing Gallery

## Adding an item to the gallery

New items can be added to the [`items.yml`](items.yml) file after which they will automatically appear on the website gallery when it is next generated.

Below is an example of an item entry:

```{yml}
- title: West Africa Diphtheria
  description: Intersectional diphtheria linelist dashboard
  href: https://apps.epicentre-msf.org/secure/app/west-africa-diphtheria
  repo: https://github.com/epicentre-msf/west-africa-diptheria-app
  access: internal
  status: active
  author: Epi DS
  date-created: '2023-10-29'
  date-modified: '2023-11-17'
  image: assets/img/epicentre_logo.png
  categories:
    - surveillance
    - diphtheria
    - nigeria
    - niger
```

#### Mandatory fields

The following fields **must** be filled for each new item:

- `title` the name of the item that will appear as a header link in the card
- `href` the URL of the content you want to share
- `access` must be either `public`or `internal` (all lowercase) depending on whether 
  the content is open to everyone or internal to MSF or a specific project
- `status` must be either `active` or `archived` (all lowercase). Assuming all new 
  entries will be `active`, but you should update this field to `archived` 
  when the report or dashboard stops being updated with new data
- `author` the name of the group/team/person who is responsible for the content
- `date-created` the date the content was first pubished in format 'YYYY-MM-DD'.
  By default, the gallery is sorted by status (active before archived) and then this date.

#### Optional fields

The following fields are optional but recommended:

- `description` a short description of the content
- `image` include your own card image by adding an image to the `assets/img/` directory
  then reference it in the `image` field. If you do not add your own image a default 
  epicentre logo will be used
- `categories` relevant categories that apply to the content like name of the disease for example.
  Ensure you do not duplicate an existing category with a different spelling etc. Look at the existing
  categories on the gallery page to verify.
- `date-modified` the date the content was last modified/updated in format 'YYYY-MM-DD'. 
  The gallery can be sorted by this date via the 'Order by' dropdown.
- `repo` a URL linking to the code repository of the project. This is not currently used but may be useful
  in the future.

## Publishing

Once you have added a new item to `items.yml` (and an image to `assets/img/` ideally), commit these changes to the main branch on github and the site will be automatically re-generated using a github action and published at https://epicentre-msf.github.io/gallery/

Github pages does use caching so you may need to hard refresh your browser to see the changes on the site.
