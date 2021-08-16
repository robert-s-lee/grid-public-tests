# setup
```
git clone https://github.com/robert-s-lee/grid-public-tests
cd public-tests
```

# test
```bash
# crate datastore
cd test1
grid datastore create --name cm-ds --source .
# wait for datastore status to be Succeeded
watch grid datastore list

# run
cd ..
grid run \
--dependency_file test1/requirements.txt \
--datastore_name cm-ds \
--datastore_version 1 \
--datastore_mount_dir cerberus_v0/ \
--instance_type g4dn.4xlarge test1/argecho.py \
--lr .000001
```

# log
```bash
grid logs hopeful-jellyfish-485-exp0
```

```log
[build] [2021-08-16T19:53:06.480111+00:00] INFO[0000] Retrieving image manifest gcr.io/grid-backend-266721/grid-images__gpu-cuda10.2-cudnn8-devel-ubuntu18.04-py3.8-torch1.7.1-pl1.2.1:manual-v12 
[build] [2021-08-16T19:53:06.480142+00:00] INFO[0000] Retrieving image gcr.io/grid-backend-266721/grid-images__gpu-cuda10.2-cudnn8-devel-ubuntu18.04-py3.8-torch1.7.1-pl1.2.1:manual-v12 from registry gcr.io 
[build] [2021-08-16T19:53:06.711414+00:00] INFO[0000] Retrieving image manifest gcr.io/grid-backend-266721/grid-images__gpu-cuda10.2-cudnn8-devel-ubuntu18.04-py3.8-torch1.7.1-pl1.2.1:manual-v12 
[build] [2021-08-16T19:53:06.711439+00:00] INFO[0000] Returning cached image manifest              
[build] [2021-08-16T19:53:06.883150+00:00] INFO[0001] Built cross stage deps: map[]                
[build] [2021-08-16T19:53:06.883182+00:00] INFO[0001] Retrieving image manifest gcr.io/grid-backend-266721/grid-images__gpu-cuda10.2-cudnn8-devel-ubuntu18.04-py3.8-torch1.7.1-pl1.2.1:manual-v12 
[build] [2021-08-16T19:53:06.883187+00:00] INFO[0001] Returning cached image manifest              
[build] [2021-08-16T19:53:06.883193+00:00] INFO[0001] Retrieving image manifest gcr.io/grid-backend-266721/grid-images__gpu-cuda10.2-cudnn8-devel-ubuntu18.04-py3.8-torch1.7.1-pl1.2.1:manual-v12 
[build] [2021-08-16T19:53:06.883197+00:00] INFO[0001] Returning cached image manifest              
[build] [2021-08-16T19:53:06.883390+00:00] INFO[0001] Executing 0 build triggers                   
[build] [2021-08-16T19:53:06.883615+00:00] INFO[0001] Checking for cached layer 302180240179.dkr.ecr.us-east-1.amazonaws.com/grid-cloud-prod:7ceabd8d3ea8109d91443deaac77c1eff0e21c0afbeec63ba6814b054b5d916b... 
[build] [2021-08-16T19:53:07.213539+00:00] INFO[0001] No cached layer found for cmd RUN pip install --no-cache-dir -r test1/requirements.txt 
[build] [2021-08-16T19:53:07.214404+00:00] INFO[0001] Unpacking rootfs as cmd COPY test1/requirements.txt /gridai/project/test1/requirements.txt requires it.

...

build] [2021-08-16T19:58:34.957535+00:00] 
[build] [2021-08-16T19:58:34.957537+00:00] conda 4.10.3 requires ruamel_yaml_conda>=0.11.14, which is not installed.
[build] [2021-08-16T19:58:34.957540+00:00] pytorch-lightning 1.3.8 requires tensorboard!=2.5.0,>=2.2.0, but you'll have tensorboard 2.5.0 which is incompatible.
[build] [2021-08-16T19:58:34.957552+00:00] Successfully installed Cython-0.29.23 Deprecated-1.2.12 Janome-0.4.1 Keras-Preprocessing-1.1.2 PyYAML-5.4.1 absl-py-0.12.0 accelerate-0.3.0 astunparse-1.6.3 bertopic-0.8.0 blis-0.7.4 bpemb-0.3.3 catalogue-2.0.4 chardet-4.0.0 click-7.1.2 cycler-0.10.0 cymem-2.0.5 dataclasses-0.6 decorator-4.4.2 deepspeed-0.4.3 diceware-0.9.6 en-core-web-lg-3.0.0 en-core-web-sm-3.0.0 filelock-3.0.12 flair-0.8.0.post1 fsspec-2021.7.0 ftfy-6.0.3 gast-0.3.3 gdown-3.13.0 gensim-3.8.3 google-auth-1.30.1 google-pasta-0.2.0 grpcio-1.38.0 h5py-2.10.0 hdbscan-0.8.27 huggingface-hub-0.0.8 hyperopt-0.2.5 importlib-metadata-3.10.1 joblib-1.0.1 kiwisolver-1.3.1 konoha-4.6.5 langdetect-1.0.9 llvmlite-0.36.0 lxml-4.6.3 matplotlib-3.4.2 mpld3-0.3 murmurhash-1.0.5 networkx-2.5.1 ninja-1.10.0.post3 nltk-3.6.2 numba-0.53.1 numpy-1.20.3 opt-einsum-3.3.0 overrides-3.1.0 pandas-1.2.4 pathy-0.5.2 plotly-4.14.2 preshed-3.0.5 protobuf-3.17.2 pyDeprecate-0.3.0 pyaml-20.4.0 pydantic-1.7.4 pynndescent-0.5.2 pytorch-lightning-1.3.8 regex-2021.4.4 requests-2.25.1 retrying-1.3.3 sacremoses-0.0.45 scikit-learn-0.24.2 scipy-1.4.1 segtok-1.5.10 sentence-transformers-1.2.0 sentencepiece-0.1.91 six-1.16.0 smart-open-3.0.0 spacy-3.0.6 spacy-legacy-3.0.5 sqlitedict-1.7.0 srsly-2.4.1 tensorboardX-1.8 tensorflow-2.2.0 tensorflow-estimator-2.2.0 tensorflow-hub-0.12.0 tensorflow-text-2.2.1 termcolor-1.1.0 thinc-8.0.3 threadpoolctl-2.1.0 tokenizers-0.10.3 top2vec-1.0.24 torch-1.7.0 torch-tb-profiler-0.2.1 torchmetrics-0.4.1 torchvision-0.8.1 tqdm-4.61.0 transformers-4.7.0 triton-0.4.2 typer-0.3.2 umap-learn-0.5.1 urllib3-1.26.5 wasabi-0.8.2 wcwidth-0.2.5 wordcloud-1.8.1 zipp-3.4.1
[build] [2021-08-16T19:58:34.957554+00:00] flair 0.8.0.post1 requires gdown==3.12.2, but you'll have gdown 3.13.0 which is incompatible.
[build] [2021-08-16T19:58:34.957594+00:00] flair 0.8.0.post1 requires numpy<1.20.0, but you'll have numpy 1.20.3 which is incompatible.
[build] [2021-08-16T19:58:34.957596+00:00] flair 0.8.0.post1 requires sentencepiece==0.1.95, but you'll have sentencepiece 0.1.91 which is incompatible.
[build] [2021-08-16T19:58:34.957599+00:00] tensorflow 2.2.0 requires tensorboard<2.3.0,>=2.2.0, but you'll have tensorboard 2.5.0 which is incompatible.
[build] [2021-08-16T19:58:39.303521+00:00] INFO[0333] Taking snapshot of files...
```
