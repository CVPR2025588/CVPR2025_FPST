# Formulated Diffusion with Transferred Attributes for Face Synthesis and Recognition
> **Abstract:** We propose the Formulated Diffusion with Transferred Attributes (FDTA) framework to synthesize faces of user-specified attributes and apply the synthesized faces to train face recognition models. Our work addresses several important issues associated with models trained on real faces, including attribute imbalance, privacy concerns, and the complexities of data annotation. The proposed FDTA framework comprises two synergistic modules: the Attribute Controllable Generator (ACG) and the Style Transfer Generator (STG). The ACG aims to create unique face images with user-specified attributes including gender, race, age, facial shape, and others. It integrates ChatGPT in the design of formulated prompts that drive a Stable Diffusion model coupled with ControlNet to generate quality face images with desired attributes. The formulated prompts are designed based on learning from interactions with ChatGPT. Given an ACG-generated face and a reference face, the STG generates a target face of the same identity as the ACG-generated face but in the style of the reference face.Our approach enables users to specify attributes and diversify styles when making synthetic data for different applications. To evaluate the effectiveness of our approach, we generated four synthetic datasets, namely Syn-MPIE, Syn-MS1M, Syn-VGGFace2 and Syn-CASIA, and compared them with their real-life counterparts. We also benchmark our approach against other state-of-the-art methods that use synthetic data for face recognition.
>
> 
## Getting Started
- Clone the repo:
    ```
    git clone https://github.com/CVPR2025588/CVPR2025_FPST.git
    ```
## Installation
```python
conda create --name FPST python=3.9
cd FPST
conda activate FPST
pip install -r requirements.txt
```
## Pretrained Models
| Architecture | Dataset      | Images (IDs×imgs)      | Link
|--------------|--------------|-----------|-----------|
| LResNet50E-IR          | Syn-MS1M | 0.5M (10K) | [Google Drive](https://drive.google.com/file/d/1BLUrw2-WTZj_r0duDQeYx-7JVxy-3tHg/view?usp=sharing) |
| LResNet50E-IR          | Syn-CASIA | 0.5M (10K×50) | [Google Drive](https://drive.google.com/file/d/1FNkr3YIX2QcTgd9Up8MLeG23DhyI2Ptn/view?usp=sharing) |
| LResNet50E-IR          | Syn-MPIE | 0.36M (2K×182) | [Google Drive](https://drive.google.com/file/d/1MPU8gNiK9E1sBe_p6kLj4juPMR4o_nQF/view?usp=sharing) |

## Training Datasets
- Syn-MS1M (10K ids/0.5M images)
  - [Google Drive](https://drive.google.com/drive/folders/1Q3sUP6mTo9ENdmKm9gLAKEPm0zIGDCpc?usp=sharing)

- Syn-MPIE (2K ids/0.36M images)
  - [Google Drive](https://drive.google.com/drive/folders/1NQgHm_CM7zgnXtq_Vs5K6Y3s3zmEu8ZT?usp=sharing)

## Validation (LFW, CFPFP, CPLFW, CALFW, AGEDB)
Please download the validation set from [insightface](https://github.com/deepinsight/insightface/tree/master/recognition/_datasets_)
```python
python verification_torch.py
```
## Comparison with SOTA Models 
![table.png](table.png)
Verification accuracy on benchmarks of Our FR model with SOTA method.Our approach shows superior handling of cross-pose challenges, notably in the CFPFP
benchmark, while DCFace is particularly adept with the age variations in AgeDB. The data reflects Syn-MS1M’s consistently higher accuracy, underscoring
the effectiveness of our approach in diverse face recognition scenarios.
