# Saved Training Commands

## Neural-Style-Transfer

```bash

floyd run --gpu --env keras "python Neural-Style-Transfer/INetwork.py
	--num_iter 100
	--rescale_image False
	--image_size 800
	--content_weight 0.025
	--style_scale 2.5
	inputs/dinosaur-2.jpg inputs/plants.jpg output/StyleSize"

# Dinosaur flowers
floyd run --gpu --env keras 'python Neural-Style-Transfer/INetwork.py --num_iter 150 --rescale_image False --image_size 600 --style_size 600 --style_scale 10 --pool_type ave --model vgg16 --min_improvement 0.5 inputs/dinosaur-2b.jpg inputs/bugs-1.jpg output/Style10Size600PoolAeBUGS'

# Stipple Style
floyd run --gpu --env keras 'python Neural-Style-Transfer/INetwork.py --num_iter 100 --rescale_image False --image_size 750 --style_size 750 --style_scale 10 --pool_type ave --min_improvement 1 inputs/target.jpg inputs/source2.png /output/Max1-sb-style10'


```

## ebsynth

```
export PATH=/root/{...}/style-transfer/ebsynth/bin:$PATH


ebsynth -style inputs/face-cut/source_style.png \
        -guide inputs/face-cut/source_Gapp.png inputs/face-cut/target_Gapp.png -weight 1.0 \
        -guide inputs/face-cut/source_Gapp.png inputs/face-cut/target_Gapp.png -weight 1.2 \
        -output output/output-ngpos-1-1.2.png

```
