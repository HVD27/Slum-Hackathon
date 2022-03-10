# Mumbai slum segmentation

More than one billion people live in slums around the world. In some developing
countries, slum residents make up for more than half of the population and lack
reliable sanitation services, clean water, electricity, other basic services. We wanted to help. We built a deep learning model to map and and monitor slum growth over time. Check out our [project site](https://cbsudux.github.io/Mumbai-slum-segmentation/) for more information and how you can be a part of this and contribute.


<p align="center">
  <img src="https://github.com/cbsudux/Mumbai-slum-segmentation/blob/master/assets/images/combined-intro.png" >
</p>

## Mumbai Slums

Mumbai is one of the most populous and wealthiest cities in India. However, it is also home to some of the world’s biggest slums -- **Dharavi, Mankhurd-Govandi belt, Kurla-Ghatkopar belt, Dindoshi and The Bhandup-Mulund slums**. The number of slum-dwellers in Mumbai is estimated to be around 9 million, up from 6 million in 2001 that is, 62% of of Mumbai live in informal slums.

![dharavi-govandi](/assets/images/dh-govandi.png)

![kurla](/assets/images/kurla.jpg)

When we spoke to the local slum dwellers, we realised that the situation was worse than we expected. Most of them lack access to clean water, basic sanitation and any form of reliable healthcare.

We wanted to help. 

## What did we do?

Any intitative on slum rehabitiation and improvement relies heavily on **slum mapping** and **monitoring**. When we spoke to the relevant authorities, we found out that they mapped slums manually (human annotators), which takes a substantial amount of time. We realised we could automate this and used a deep learning approach to **segment and map individual slums from satellite imagery**. In addition, we also wrote code to **perform change detection and monitor slum change over time**. Slum change detection is an important task and analysing increase/decrease of a slum can provide valuable insights.

## How did we go about it?

We curated a **dataset** containing 3-band (RGB) satellite imagery with 65 cm per pixel resolution
collected from Google Earth. Each image has a pixel size of 1280x720. The satellite imagery covers most of
Mumbai and we include images from 2002 to 2018, to analyze slum change. We used 513 images for training, and 97 images for testing. (Unfortunately, we cannot redistribute the dataset, due to Google policy.)

For **slum segmentation and mapping**, we trained a Mask R-CNN on our custom dataset. Check our [github readme](https://github.com/cbsudux/Mumbai-slum-segmentation/tree/master/slums) for our training and testing approaches, and our [paper](https://arxiv.org/abs/1811.07896) for more details.  

![kurla result](/assets/images/kurla-result_2.png)

For **slum change detection**, we took a pair of satellite images, representing the same location at different points of time. We predicted masks for both these images and then subtracted the masks to obtain a percentage icrease/decrease. The following images (below) show a change of +35.25% between 2018 (top row) and 2005 (bottom row) of the same slum.    

![change result](/assets/images/change.png)

## Training and Testing

Read [this](https://github.com/cbsudux/Mumbai-slum-segmentation/tree/master/slums) for training and testing, and how to prepare your own satellite dataset.



## Acknowledgements

We would like to thank the Slum Rehabiliation Authority of Mumbai for their data.

## Citing

We published our work in the NeurIPS (NIPS) 2018 ML4D workshop. If you'd like to use our research, please cite using :
```
@article{maiya2018slum,
  title={Slum Segmentation and Change Detection: A Deep Learning Approach},
  author={Maiya, Shishira R and Babu, Sudharshan Chandra},
  journal={arXiv preprint arXiv:1811.07896},
  year={2018}
}
```

## License

<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br />This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.



