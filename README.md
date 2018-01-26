# codelab tensorflow

###### see "TensorFlow for poets 2"

https://github.com/googlecodelabs/tensorflow-for-poets-2




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
