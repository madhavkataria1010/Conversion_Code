# Conversio_Code

## Download Files

Download files befpre running

- **[Converted Model Files](https://drive.google.com/drive/folders/1yTpvPSyEEDprL6KRTTQr6ewQDMGoEB1M?usp=sharing)**
- **[TensorFlow Model](https://drive.google.com/file/d/17AVNTgjJmVyP_4CBnncXY8OJEbqIEhhN/view?usp=sharing)**

## Prerequisites

- All dependencies listed in `requirements.txt`

## Model Conversion

To convert a TensorFlow model to a PyTorch model, use the following command:

```bash
python run_convert_from_tf.py --input=2019-02-18-stylegan-faces-network-02041-011095.pkl --output=checkpoint
```

### Arguments

- `--input`: Path to the input TensorFlow model file (`.pkl`).
- `--output`: Directory where the converted PyTorch model will be saved.

After running the command, the converted model will be saved in the `checkpoint` directory.

## Generating Images

Once the model is converted, you can generate images using the following command:

```bash
python run_generator.py generate_images --network=checkpoint/Gs.pth --seeds=66,230,389,1518 --truncation_psi=1.0
```

### Arguments

- `--network`: Path to the converted PyTorch model (`.pth` file).
- `--seeds`: A comma-separated list of seeds for generating images.
- `--truncation_psi`: Controls the truncation of the latent space (values between 0.0 and 1.0, with 1.0 being no truncation).
