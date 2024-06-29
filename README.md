# De-SaTE: Denoising Self-attention Transformer Encoders for Li-ion Battery Health Prognostics
This repository contains the code for De-SaTE: Denoising Self-attention Transformer Encoders for Li-ion Battery Health Prognostics

### Citation
#### Bibtex
```
@inproceedings{desate,
  author={Shinde, Gaurav and Mohapatra, Rohan and Krishan, Pooja and Sengupta, Saptarshi},
  booktitle={2023 IEEE International Conference on Big Data (BigData)}, 
  title={De-SaTE: Denoising Self-attention Transformer Encoders for Li-ion Battery Health Prognostics}, 
  year={2023},
  volume={},
  number={},
  pages={2221-2228},
  doi={10.1109/BigData59044.2023.10386134}}
```
#### In text
G. Shinde, R. Mohapatra, P. Krishan and S. Sengupta, "De-SaTE: Denoising Self-attention Transformer Encoders for Li-ion Battery Health Prognostics," 2023 IEEE International Conference on Big Data (BigData), Sorrento, Italy, 2023, pp. 2221-2228.

### De-SaTE Architecture 
![image](https://github.com/GauravYS/Job-Portal-Application/assets/116845183/c006276c-3949-43c1-8be9-fdd1c51855a0)

#### In text
G. Shinde, R. Mohapatra, P. Krishan and S. Sengupta, "De-SaTE: Denoising Self-attention Transformer Encoders for Li-ion Battery Health Prognostics," 2023 IEEE International Conference on Big Data (BigData), Sorrento, Italy, 2023, pp. 2221-2228.

### Steps to run 
   1) Change the mask function to incorporate various types of noise
      - Gaussian noise:
           corrupted_x = x + self.noise_level * torch.randn_like(x)
      - Poisson noise:
           rate = torch.abs(x) / (self.noise_level + 1e-6)  # Adding a small epsilon to avoid division by zero
           poisson_noise = torch.poisson(rate) * (self.noise_level + 1e-6)
           corrupted_x = x + poisson_noise
       - Speckle noise:
           corrupted_x = x * (1 + self.noise_level * torch.randn_like(x))
       - Uniform noise:
           corrupted_x = x + self.noise_level * (torch.rand_like(x) - 0.5)
         Change the wavelet_denoise function according to soft , hard and garrote mode:
           Wavelet decomposition
           Threshold for denoising
           Reconstruct the denoised signal
         
    2) Run the training loop for ## number of epochs

### Experiments
#### NASA 






