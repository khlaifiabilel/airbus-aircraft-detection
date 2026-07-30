# Airbus Aircrafts Detection Sample Dataset

This dataset is a demonstration version of larger and more advanced deep learning datasets created from Airbus satellite imagery. It is provided for demonstration purpose only.

> [!IMPORTANT]
> This is an independent project copy, not an official Airbus repository. Airbus supplied the sample imagery and dataset description, Airbus DS Intelligence curated the dataset, and Appen supplied the annotations. The repository also contains a separate YOLOv5 experiment and generated artifacts described below.

## Repository scope and provenance

The Git history begins with a single import commit and does not preserve a source repository or earlier dataset history. The Airbus sample consists of:

- `images/`: 103 annotated Pléiades image extracts
- `annotations.csv`: 3,425 aircraft annotations plus the header row
- `extras/`: 6 unannotated images
- `LICENSE.txt`: the CC BY-NC-SA 4.0 license text supplied with the data

Repository-specific experiment material includes:

- `aircraft-detection-with-yolov5.ipynb`, which converts the polygon annotations into tiled, single-class YOLO labels and invokes YOLOv5 training and detection
- `train/` and `val/`, the generated 512 x 512 image tiles and YOLO labels
- `dataset.yaml`, which contains the original author's absolute local paths and must be reviewed before reuse
- `wandb/`, saved Weights & Biases run metadata and outputs from December 2021
- `yolov5s.pt`, a pretrained YOLOv5 checkpoint
- `yolov5`, a Git link pinned to Ultralytics YOLOv5 commit [`dc54ed5`](https://github.com/ultralytics/yolov5/commit/dc54ed5763720ced4f6784552c47534af5413d45); the repository does not include a `.gitmodules` URL, so a normal clone does not populate it

The notebook records the experiment as run from `/home/bilel/GitHub/Airbus-Aircraft-Detection`, installs from the then-current Ultralytics YOLOv5 repository, requires an interactive Weights & Biases login, and uses machine-specific paths. It is an experiment record, not a portable or currently validated training recipe.

## Background

[Airbus Defense and Space Intelligence](https://www.intelligence-airbusds.com/) operates the largest commercial satellite constellation combining optical imagery from Pléiades, SPOT, Vision-1 and DMC as well as the radar constellation (consisting of TerraSAR-X, TanDEM-X and PAZ). We are further expanding our sensor capabilities with the upcoming Pléiades Neo constellation providing higher resolution, greater revisits and more acquisition capabilities.

[OneAtlas](https://oneatlas.airbus.com/) provides flexible and easy access to Airbus premium satellite imagery, innovative geospatial analytics, industry-specific insights and more.

## Imagery for training

The `images` folder contains 103 extract of Pleiades imagery at roughly 50 cm resolution. Each each image is stored as a JPEG file of size 2560 x 2560 pixels (i.e. 1280 meters on ground). The locations are various airports worldwide. Some airports appear multiple time at different acquisition dates. Some images also include fog or cloud for diversity.

## Annotations

All aircrafts have been annotated with bounding boxes on the provided imagery. The annotations are provided in the form of closed GeoJSON polygons. A CSV file named `annotations.csv` provides all anotations - one annotation per line with the corresponding filename of the image as `image_id` and the class of the annotation, mainly `Aircraft` or `Truncated_Aircraft` for aircrafts located at the border of the image.

## Extra imagery

A folder named `extras` contains 6 extra images which are not annotated but could be used to test a model on new - unseen before - images. 

## License

The Airbus sample data is licensed under the [**Creative Commons BY-NC-SA 4.0 International**](LICENSE.txt) license:

You are free to :
- **Share** — copy and redistribute the material in any medium or format
- **Adapt** — remix, transform, and build upon the material

as long as you follow the following terms:
- **Attribution** — You must give appropriate credit, provide a link to the license, and indicate if changes were made. You may do so in any reasonable manner, but not in any way that suggests the licensor endorses you or your use.
- **NonCommercial** — You may not use the material for commercial purposes.
- **ShareAlike** — If you remix, transform, or build upon the material, you must distribute your contributions under the same license as the original.

The repository also contains third-party YOLOv5 code references and a model checkpoint. Do not assume the dataset license replaces their applicable upstream terms. No ownership of Airbus imagery, Appen annotations, Ultralytics code, or third-party model assets is claimed here.

## Contact

**We welcome feedback and comments!** This dataset was curated by `jeffaudi` for [Airbus DS Intelligence](https://www.intelligence-airbusds.com/) and annotations provided by [Appen](https://appen.com/).

Please contact our [sales team](https://www.intelligence-airbusds.com/contact/) for any question related to our satellite imagery offer or to our **OneAtlas** digital services.
