# aws-deep-learning

In the aws deep learning project we used Deep Learning to create poetry and paintings.

## Paintings

We use a generative adversarial network (GAN) to create images of female artists. Our is based on the wikiart data (https://www.wikiart.org/), which was searched for paintings by artists contained in the wikipedia list of female artists https://en.wikipedia.org/wiki/Lists_of_women_artists. Selecting only those yielded a dataset of 66 artists and 2632 images.

### Technical details
#### The model

#### Installation 
1. Launch habana instance https://docs.habana.ai/en/latest/AWS_EC2_Getting_Started/AWS_EC2_Getting_Started.html 
2. Install Synapse 
```bash
	wget https://raw.githubusercontent.com/HabanaAI/Setup_and_Install/main/installation_scripts/synapse_installation.sh . 
```

3. Install habana drivers https://docs.habana.ai/en/latest/Installation_Guide/GAUDI_Installation_Guide.html#habana-deep-learning-ami

4. Load drivers 
```bash
	sudo modprobe  habanalabs
	sudo modprobe  habanalabs_en
```

5. Check habana drivers 
```bash
	hl-smi
```

6. Install tensorflow dependencies
```bash
	wget https://raw.githubusercontent.com/HabanaAI/Setup_and_Install/main/installation_scripts/TensorFlow/tensorflow_installation.sh . 
	source ~/.bashrc
 ```

7. Install python dependencies to run the GAN.py 

```bash
	pip install -r requirements.txt 
```

#### Use Habana drivers 
Add the following lines at the python script 

```python
	import habana_frameworks.tensorflow as htf
	htf.load_habana_module()
```

## Load dataset 

Configure GAN.py with the following parameters when training:
```python
	inputpath="Female_painters/*"
	loadNewData =True 
```

Setting the directory where the data is and the boolean loadNewData True means that new data is loaded and the training_data.npy file is generated. Therefore in futrure training of the GAN with the same data it is not necessary to load the folder again. 

#### Execute GAN

```bash
	python3 GAN.py
```

Intermadiate results would be at generated_images and models folders 

