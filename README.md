# BingDatasetPrepare
This code prepares a graphical dataset for training your neural network using the Bing platform and uses the bing-image-downloader library.

This is the python code i used in the google colab platform.
It works like this:
1. In the list variable, you enter a list of search queries (in the example, these are dog breeds)
```
list = ["Brittnepoo",
"Broodle Griffon",
"Brussels Griffon",
"Brussels Griffon Mix",
"Bugg",
"Bull Mastiff Hybrid",
................
"Yorkiepoo",
"Yorkshire Terrier",
"Yorkshire Terrier Mix",
"Yorktese"]
```
2. The limitmax variable is responsible for the total number of images per request
3. Variables folder_test, folder_train, folder_valid are responsible for the path to the corresponding folders where the images will be stored. For each search query, images will be shared as follows:

- folder_test - 20%
- folder_train - 40%
- folder_valid - 40%

Since the dataset usually takes a large amount of data, and google colab provides a small amount of storage, I connect a google drive and save the dataset to it.
```
from google.colab import drive
drive.mount('/content/gdrive')
```
4. To speed up the download process, the work is divided into 6 parallel threads.
