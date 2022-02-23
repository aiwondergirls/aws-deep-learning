# aws-deep-learning

## Installation 
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


