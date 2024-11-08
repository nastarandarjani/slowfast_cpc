# Implementation

## Data Preparation

1. **Download Dataset Splits**  
   Obtain the dataset's [train/val/test split](/kinetics-dataset/README.md#kinetics-400-info).

2. **Set Up Annotations**  
   Create an `annotations` directory and place the following files for each split:
   - `.txt` files containing video links.
   - Annotation links.
   - Prepared `.csv` files, following the [PyTorchVideo recommendations](https://github.com/facebookresearch/pytorchvideo/docs/source/data_preparation.md#kinetics). You can generate these using the [`create_csv.sh`](/kinetics-dataset/create_csv.sh) script.

3. **Downscale Videos**  
   Resize videos to a short edge size of 256 pixels, as recommended by [PyTorchVideo](https://github.com/facebookresearch/pytorchvideo/docs/source/data_preparation.md#kinetics). I implemented a job script [`downsample.sh`](/kinetics-dataset/downsample.sh) to execute the Python script [`downscale_video.sh`](/kinetics-dataset/downscale_video.sh).

   **Note:** Update the following variables in `downscale_video.py` according to your needs:
   ```python
   14 file_src = "annotations/val_output.csv"
   15 folder_path = "val/"
   16 output_path = "val_256/"
   ```

4. **Backup and Organize Files**

   Convert the split folders into `.tar` files, both in raw format and downsampled form. Store these files as follows:
      - Backup in `~/nearline/def-shahabkb/nasi14`.
      - High-speed I/O storage in `~/scratch/`.

   The directory structure is as follows:
   ```
   k400
   ├── downsampled
   │   ├── test.tar
   │   ├── train.tar
   │   └── val.tar
   └── raw
      ├── test.tar
      ├── train.tar
      └── val.tar
   ```