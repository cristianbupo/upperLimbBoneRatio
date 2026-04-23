# Allometry of the forelimb bones in amniota animals

## Aim

This project search to stablish allometries of the amniota forelimbs' bones.

## Details

__Why:__ This will help determine possible domain geometry ratios for developing directional diffusion systems to explain the development of the forelimb and provide an explanation for the variety of forelimbs that exist.

__Animal selection:__ The ***amniota*** taxonomy is chosen because they develop as tetrapods and all develop inside an amniotic sac, either inside an egg or in the uterus.

__Source__: [Morphosource](https://www.morphosource.org/?locale=en)

__Search criteria__: 

- Complete bones already 3d reconstructed of adult(?) animals.
- Non-extints animals
- Forelimbs bones:
  - Humerus (k)
  - Radius (k)
  - Ulna (k)
  - Matacarpal (c)
  - Phlanges (c)

In Morphosource, search for the name of the bone and filter according to the GBIF taxonomy. I don't know if there is a better way, but I propose filtering by Chordata only, and then selecting the Amniota animals manually (there is no Amniota filter), by looking (in google?) to see if the animal is amniota. 

To avoid losing time, perhaps avoid CT images, like that we don't need to do recontructions. 

Another thing to consider is that the dimensions are sometimes incorrect. Sometimes the scans are done in millimetres, centimetres or metres – no one agrees. I just hope that no one uses imperial units :/ 

__Bones procedure:__

1. Download bones (3D object)
2. Change the name of the file with the ID od the bone, as it is in Morphosource
3. Try to put it in the folder of the bone
4. How to save the info??? 
   - We talked about SQL, I'm not expert (I know nothing), but open to learn.
   - Else, I think *.JSON* structure should be fine.


This is just a draft, I'll try to think more about it.

``` json 
{
  "specimen_id": "",
  "taxon": {
    "scientific_name": "",
    "clade": "Amniota",
    "NCBI": "",
  },

  "bone": {
    "element": "humerus | radius | ulna | MC_I | MC_II | MC_III | MC_IV | MC_V | same fore phalanges ",
    "side": "left | right",
  },

  "scan": {
    "doi": "",
    "ARK": ""
  },

  "measurements": [
    {
      "measurement_id": "humerus_length",
      "description": "maximum proximodistal length",
      "value": null,
      "unit": "mm",
      "method": "landmarks | bounding_box | manual",
      "landmarks_used": ["proximal_point", "distal_point"],
      "coordinate_system": "bone_local",
      "repeat": 1
    },
    {
      "measurement_id": "midshaft_diameter_ap",
      "description": "anteroposterior diameter at 50% length",
      "value": null,
      "unit": "mm",
      "method": "cross_section",
      "section_location": 0.5
    }
  ],

  "landmarks": [
    {
      "name": "proximal_head_center",
      "coordinates": [0, 0, 0],
      "definition": "center of articular surface"
    }
  ],
}
```
  