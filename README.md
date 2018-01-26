# codelab tensorflow

###### see "TensorFlow for poets 2"

https://github.com/googlecodelabs/tensorflow-for-poets-2

https://codelabs.developers.google.com/codelabs/tensorflow-for-poets/#0


#
use python 3

###### Setup

```
virtualenv codelab -p python3
```
`-p python3` not needed for systems with python 3 as the default


###### Activate

(for unix like machines)
```
source codelab/bin/activate
```

(for mingw on windows machines)
```
source codelab/Scripts/activate
```


###### Install

```
pip install -r requirements.txt
```


###### Download data

```
mkdir tf_files
```

```
curl http://download.tensorflow.org/example_images/flower_photos.tgz | tar xz -C tf_files
```


### Step 1

```
export IMAGE_SIZE=224
export ARCHITECTURE="mobilenet_0.50_${IMAGE_SIZE}"
```

train the neural network with 500 iterations
```
python -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --how_many_training_steps=500 \
  --model_dir=tf_files/models/ \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=tf_files/flower_photos
```

after the training run tensorboad
```
tensorboard --logdir tf_files/training_summaries &
```


train the neural network fully
```
python -m scripts.retrain \
  --bottleneck_dir=tf_files/bottlenecks \
  --model_dir=tf_files/models/"${ARCHITECTURE}" \
  --summaries_dir=tf_files/training_summaries/"${ARCHITECTURE}" \
  --output_graph=tf_files/retrained_graph.pb \
  --output_labels=tf_files/retrained_labels.txt \
  --architecture="${ARCHITECTURE}" \
  --image_dir=tf_files/flower_photos
```

