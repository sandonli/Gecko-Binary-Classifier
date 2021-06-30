# Gecko-Binary-Classifier

A binary classifier that is able to differentiate between the Gold Dust Day Gecko and the Giant Day Gecko, through the use of transfer learning on a pre-trained ResNet18 model. This classifier is able to correctly classify samples roughly 95% of the time.

<h2>Description of Gecko Species</h2>
<p>Gold Dust Day Geckos have bodies that are usually different shades of green (sometimes blue), with three orangish red bars that go across the head, and three more orangish red bars that go along the body of the animal. Gold Dust Day Geckos are also characterized by blue skin on the upper part of their eyes and the red and gold specks that run across their body. Giant Day Geckos have bodies that are usually bright green (sometimes bluish green) and are littered with red dots or bars. A red stripe extends from the nostril of the gecko to the eye. Both species of gecko are from northern Madagascar and are commonly kept as pets.<p/>

<p>To distinguish the Gold Dust Day Gecko from the Giant Day Gecko, one could either look at the eye of the gecko (Gold Dust Day Gecko eyes have blue skin on the upper part, while Giant Day Geckos do not) or the head (gold dust day geckos have 3 red stripes across their head, while giant day geckos have a stripe from the nostril to the eye). One could also look at the three red stripes across a gold dust day gecko's back, as it's unlikely that a giant day gecko will have the same pattern. Gold dust day geckos also have golden spots that could help in the identification of it. Lastly, giant day geckos are significantly larger than gold dust day geckos.<p/>

<h2>Dataset</h2>
<p>https://github.com/ostrolucky/Bulk-Bing-Image-downloader was used to scrape the images from Bing, while https://github.com/KiranKumarChilla/Removing-Duplicate-Docs-Using-Hashing-in-Python was used to remove any exact duplicates in the dataset. The goal was to have 500 images for each dataset. The code for generating the datasets can be found in the GeckoDatasetRetrieval notebook.<p/>


After processing both datasets, I ended up rejecting 180 images from the giant day gecko dataset and 125 images from the gold dust day gecko dataset, for reasons listed below. Since many of the images were removed for the same/similar reasons, only one image, which represents a reason, will be documented. These rejected images can be found in the dataset rejects directory.

**Gold Dust Day Gecko:**
- 3x92qbueju831: image of a gecko enclosure<br/>
- tumblr_peo7jihmpb1sukdwj_1280: hard to identify as a gold dust day gecko or not identifiable<br/>
- tarantulas-for-sale: unrelated to geckos<br/>
- web-3: not a gold dust day gecko/incorrect gecko species<br/>
- il_570xN.671107052_pufi: duplicate of an image that already exists in the dataset<br/>
- 200px-Gold_dust_day_gecko_with_a_bab: poor image quality<br/>
- 1509341447.dorkusmalorkus_day_gecko: not a real gold dust day gecko<br/>

**Giant Day Gecko:**
- $_86: image of a gecko enclosure
- 1fe44f4e5b653b7b786468566b625af4: hard to identify as a giant day gecko or not identifiable
- 3Rivb.OvCc.1: unrelated to geckos
- 12a1fe3bcc22cdf9e75251a67f622ef7: not a giant day gecko/incorrect gecko species
- Crimson-Giant-Day-Geckos-face_000_lg: duplicate of an image that already exists in the dataset
- giant_day_gecko_1: poor image quality
- giant_day_gecko_by_yue1920-d9p9v3z: not a real giant day gecko

After rejecting the images, I chose to manually refill the datasets back up to 500, trying my best to avoid adding duplicates. I used google images for this.

<h2>Training and Testing<h2/>
 <p>
