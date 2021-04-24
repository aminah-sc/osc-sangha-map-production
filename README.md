<span xmlns:dct="http://purl.org/dc/terms/" xmlns:vcard="http://www.w3.org/2001/vcard-rdf/3.0#">
  <a rel="license"
     href="http://creativecommons.org/publicdomain/zero/1.0/">
    <img src="https://licensebuttons.net/p/zero/1.0/80x15.png" style="border-style: none;" alt="CC0" />
  </a>
</span>

(Working draft)

# Sangha Map 
Developed for the [Open Sangha Collective](https://opensanghacollective.org/); useable by whomever.

## 💡 Initial Spec

> Creating a custom, growable google map that we can embed on the wordpress site that we and interested visitors to our site can gradually grow to be a thoroughly comprehensive map of monastic buddhist communities around the world. Just to give you the full picture we want users to be able to pin a site on but we want to be able to verify it before their addition becomes fixed / public. Hopefully that is possible. Also we would ideally be able to capture quite al ot of info about each place. Name, tradition, location, website, telephone, name of abbot, photos etc. What do you think? Doable?
>
> …
>
> this is the page it will go on:
>
> https://opensanghacollective.org/traditional-buddhist-communities/
>
> It really is about forging links between lay practice and the monastic sangha so I would say do not include a dharma centre where there is no monastic presence … But it is no problem if those boundaries are not strictly adhered to and tend towards including gray areas rather than excluding them. One thing that would be great is to make sure that we include a wide variety of of wats, viharas and temples across the lineages so zen, chan, son, thien, shingon, Tientai, vajrayana etc as well as a variety from within the theravada tradition (sri lankan, burmese, thai, laotion, cambodian etc). Another thing to consider is that we want some geographic spread across all the continents (though Antarctica may be tricky...).
>
>…
>
> we realised that for the map to help with our aim of helping people connect with the monastic Sangha one thing it would need would be a way of indicating whether each monastic community had confirmed with us that they accepted live in lay practitioners on a Dana basis. Could this be built in? I’m thinking a key or asterisk type thing to indicate this function has been confirmed.


## 🤔 Porject Plan Sketch:

- Build map with:
  - [Gatsby](https://www.gatsbyjs.com/)
  - [Google Maps API](https://developers.google.com/maps/documentation/javascript/overview)
  - [react-google-maps/api](https://react-google-maps-api-docs.netlify.app/)
- Collect & clean exisiting data
  - manual search
  - [Places APIs](https://developers.google.com/maps/documentation/places/web-service/overview)
- Host repo on GitHub
- Deploy to Netlify
- Embed with `iframe` 
- Rinse & repeat: data collection, clean, update & UI/UX development


### Place Inclusion Criteria

- The community follows [Vinaya](https://suttacentral.net/pitaka/vinaya) based ordination (see [intro to the Vinaya](https://suttacentral.net/vinaya)).
- By case by case assesment for boarder cases.

#### Verified property values:

- `true`
- `tentative`
- `verified, accepts lay residents`
- `duplicate`
- `false`


### Working Data Schema

```
{   
  "properties": {
    "geometry": {
        "location": {
          longitude,
          latitude
        }
      },
      "name": "",
      "address": "",
      "telephone": "",
      "website": "",
      "description": "",
      "photos": [],
      "video": [],
      "audio": [],
      "tradition": ""
      "monastics": [],

  },
  "meta": {
      "verified": "false",
      "last_updated": ""
  }
}
```

### So Far:

- Working map built
- 3743 records taken from the Places API, of which:
- 1760 places marked as tentatively varified (places with "vihara", "monastery", "wat", "temple", or "hermitage" in the place name)

### Next Steps:

- Refine data
- WP intergration
- Image retrieval
- UI/UX improvement (search, full data display, key, location url +)
- design contribution & maintanence strategy




<!-- AUTO-GENERATED-CONTENT:END -->
