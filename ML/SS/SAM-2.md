
# External Links

Meta
https://ai.meta.com/sam2/
https://ai.meta.com/blog/segment-anything-2-video/

TG
https://t.me/ai_newz/3086

GH
https://github.com/facebookresearch/segment-anything-2

# Summary

**Key moments**
- Video segmentation
- SA-V dataset
- Apache 2.0

**Performance**
- 130 FPS on a single A100
- six times faster than SAM?

**Evaluation**
- 17 zero-shot video datasets
- video object segmentation benchmarks
	- DAVIS, MOSE, LVOS, YouTube-VOS

**Terms**
- masklet
	- spatio-temporal mask

# Links

[[SAM]]

**Tasks**
[[Semantic Segmentation]]
[[Tracking]]


Amazon SageMaker
?

# Overview

**Usage**
- VLM
	-  multimodal understanding of the world
	- *could be a component as part of a larger AI system*
- AR glasses

**SAM methodology**
- new task
- new model
- new dataset

**Video segmentation**
video segmentation problem
- important for
	- mixed reality
	- robotics
- challenges
	- *Videos are often lower quality than images due to camera motion, blur, and lower resolution*

**Process**
- immediate prediction of the mask on the current frame
- temporally propagates it to generate the masklet of the target object across all video frames
- initial masklet

**Prompts**
- clicks (positive or **negative**)

**Ambiguity**
- *multiple valid masks when faced with ambiguity*
	- like SAM
- *ambiguity can extend across video frames*
	- example with tire and motorbike

**Occlusion**
- *In video, it’s possible for no valid object to exist on a particular frame*
- Occlusion head
	- new module 

**Limitations**
- Accuracy
	- Conditions
		- long occlusions
		- crowded scenes
		- extended videos
	- Errors
		- wrong re-id
- Efficiency
	- Multiple objects
		- *Under the hood, SAM 2 processes each object separately*
		- ???

**Features**
- Multiple objects
	- *SAM 2 supports the ability to segment multiple individual objects simultaneously*
	- id?

# Memory

memory mechanism
temporal components

*model needs to rely on memory*

*When applied to images, the memory components are empty and the model behaves like SAM.*

**components**
- memory attention
- memory encoder
- memory bank

*Memories of frames are created by the memory encoder based on the current mask prediction and placed in the memory bank for use in segmenting subsequent frames.*

**memory bank**
- memories from previous frames
- prompted frames
- queue size?
	- will it contain too much of memories for long video?
	- last N frames?

**memory attention**
- *memory attention operation takes the per-frame embedding from the image encoder and conditions it on the memory bank*
	- Heavy encoder runs on each frame?
	- real-time processing?
	- see **Performance**
- How memory attention block works in details?

**streaming architecture**
real-time processing of arbitrarily long videos


# Data


SA-V dataset
- 50к annotated videos
- 600к masklets
- Videos featuring geographically diverse
	- 47 countries

**Datasets**
- only for initial training?
- leverage the SA-1B image dataset
- Existing datasets
	- *additional internal licensed video dataset*
	- examples?

data engine
- model-in-the-loop
- human-in-the-loop
- Annotation tool for video
	- *8.4 times faster than using SAM per frame*
	- *faster than combining SAM with an off-the-shelf tracker*
		- example of such tracker?
	- How it was made?
		- How was made annotation tool for video?
		- How was setuped annotation process for video?