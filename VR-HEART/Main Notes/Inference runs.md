
### Experiment 1
transforms used
```
test_transforms = Compose([
LoadImaged(keys=["image","label"]),
EnsureChannelFirstd(keys=["image","label"]),
EnsureTyped(keys=["image","label"]),
ResizeWithPadOrCropd(keys=["image","label"], spatial_size=(512,512,288)),
ConvertToMultiChannelBasedOnImageCHDClassesd(keys="label"),
Orientationd(keys=["image","label"], axcodes="RAS"),
Spacingd(keys=["image"], mode=["bilinear"], pixdim=[1,1,1]),
NormalizeIntensityd(keys=["image"], nonzero=True, channel_wise=True),
])

  
post_transforms = Compose([
Activationsd(keys="pred", sigmoid=True),
AsDiscreted(keys="pred", threshold=0.5),
])
```

results
![[Pasted image 20240814184437.png]]

### Experiment 2

transforms used:

```test_org_transforms = Compose([
LoadImaged(keys=["image", "label"]),
EnsureChannelFirstd(keys=["image"]),
ConvertToMultiChannelBasedOnImageCHDClassesd(keys="label"),
Orientationd(keys=["image"], axcodes="RAS"),
Spacingd(keys=["image"], pixdim=(1.0, 1.0, 1.0), mode="bilinear"),
NormalizeIntensityd(keys="image", nonzero=True, channel_wise=True),
])

post_transforms = Compose([
	Invertd(
	keys="pred",
	transform=test_org_transforms,
	orig_keys="image",
	meta_keys="pred_meta_dict",
	orig_meta_keys="image_meta_dict",
	meta_key_postfix="meta_dict",
	nearest_interp=False,
	to_tensor=True,
	device=device,
),
	Activationsd(keys="pred", sigmoid=True),
	AsDiscreted(keys="pred", threshold=0.5),
])
```

Results:
![[Pasted image 20240819144203.png]]


### Experiment 3

```test_org_transforms = Compose([
LoadImaged(keys=["image", "label"]),
EnsureChannelFirstd(keys=["image"]),
EnsureTyped(keys=["image","label"]),
ConvertToMultiChannelBasedOnImageCHDClassesd(keys="label"),
Orientationd(keys=["image"], axcodes="RAS"),
Spacingd(keys=["image"], pixdim=(1.0, 1.0, 1.0), mode="bilinear"),
NormalizeIntensityd(keys="image", nonzero=True, channel_wise=True),
])

post_transforms = Compose([
	Invertd(
	keys="pred",
	transform=test_org_transforms,
	orig_keys="image",
	meta_keys="pred_meta_dict",
	orig_meta_keys="image_meta_dict",
	meta_key_postfix="meta_dict",
	nearest_interp=False,
	to_tensor=True,
	device=device,
),
	Activationsd(keys="pred", sigmoid=True),
	AsDiscreted(keys="pred", threshold=0.5),
])
```

Results:

![[Pasted image 20240819144947.png]]

### Experiment 4

transforms used:

```test_org_transforms = Compose([
LoadImaged(keys=["image", "label"]),
EnsureChannelFirstd(keys=["image"]),
ConvertToMultiChannelBasedOnImageCHDClassesd(keys="label"),
Orientationd(keys=["image"], axcodes="RAS"),
Spacingd(keys=["image"], pixdim=(1.0, 1.0, 1.0), mode="bilinear"),
NormalizeIntensityd(keys="image", nonzero=True, channel_wise=True),
])

post_transforms = Compose([
	Activationsd(keys="pred", sigmoid=True),
	AsDiscreted(keys="pred", threshold=0.5),
])
```

Results:

![[Pasted image 20240819151626.png]]



### Experiment 5

transforms used:

```
test_org_transforms = Compose(
[
LoadImaged(keys=["image","label"]),

EnsureChannelFirstd(keys=["image","label"]),

EnsureTyped(keys=["image","label"]),

ResizeWithPadOrCropd(keys=["image","label"], spatial_size=(512,512,288)),

ConvertToMultiChannelBasedOnImageCHDClassesd(keys="label"),

Orientationd(keys=["image","label"], axcodes="RAS"),

Spacingd(keys=["image","label"], mode=["bilinear", "nearest"], pixdim=[1,1,1]),

]

)

  

post_transforms = Compose(

[

Activationsd(keys="pred", sigmoid=True),

AsDiscreted(keys="pred", threshold=0.5),

]

)
```

Results:

![[Pasted image 20240821210637.png]]


