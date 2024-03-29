# SafeComm-Digital-Security-Solutions---284051

# **Project 4: SafeComm Digital Security Solutions - BERNARDINI Margherita, AUGELLO Ginevra, DESIDERI Ernesto**

## **Task overview**
The main goal of this project is to design and apply a model which is able to automatically identify fraudolent messages.
In order to carry out this spam detection task, we will be using a dataset, containing both malicious and regular text messages.
The dataset, sms_df, is comprised of the following features:
*   **Fraudolent**: A binary indicator of the nature of the message (0 for *non fraudolent* and 1 for *fraudolent*).
*   **SMS test**: The content of the messages.
*   **ID**: A unique identifier for each SMS.
*   **Date and Time**: A timestamp, indicating when the message was sent.

## **Our solutions and environment**
After carrying out an exploratory data analysis (EDA) and after having preprocessed the data available, we identified the problem proposed as a classification problem.
Because we were dealing with high dimensional data - particularly the text data contained within the column *SMS test* - we excluded tree models and we decided to focus on four other models, specifically:
*  **k-Neighbors for classification**
*  **Logistic Regression**
*  **Kernelized Support Vector Machines (with 'rbf' kernel)**
*  **Multilayer Perceptron**

For the sake of completeness, we decided to try out multiple possible options, as they would be great for
comparison purposes.
Each model was given the data contained within sms_df, after splitting the dataset into a train set and a test set. Performances and results were then evaluated, as we will see later.

### **Regarding preprocessing: feature selection & engineering**
The steps taken during the preprocessing phase are carefully described within our notebook. Despite this, we believe that it is important to reiterate some concepts regarding the features that
we decided to include, those that have been excluded and the ones that have been added. In this section, we will provide an overview of this topic, as it is part of our design choices:
*  The features *ID* and *Date and Time* were excluded, as they were of little relevance to the classification task.
*  Additional features (*Text Length, Special Characters, Num Uppercase, Numeric Count, Keywords count*) were included because they were deemed useful to handle the problem at hand during the EDA.

### **Regarding the environment**
This is our conda list



```
# Name                    Version                   Build  Channel
aiohttp                   3.8.5           py311h2bbff1b_0
aiosignal                 1.2.0              pyhd3eb1b0_0
anaconda-anon-usage       0.4.2           py311hfc23b7f_0
anaconda-catalogs         0.2.0           py311haa95532_0
anaconda-client           1.12.1          py311haa95532_0
anaconda-cloud-auth       0.1.4           py311haa95532_0
anaconda-navigator        2.5.0           py311haa95532_0
anaconda-project          0.11.1          py311haa95532_0
anyio                     3.5.0           py311haa95532_0
appdirs                   1.4.4              pyhd3eb1b0_0
archspec                  0.2.1              pyhd3eb1b0_0
argon2-cffi               21.3.0             pyhd3eb1b0_0
argon2-cffi-bindings      21.2.0          py311h2bbff1b_0
asttokens                 2.0.5              pyhd3eb1b0_0
async-timeout             4.0.2           py311haa95532_0
attrs                     23.1.0          py311haa95532_0
backcall                  0.2.0              pyhd3eb1b0_0
backports                 1.1                pyhd3eb1b0_0
backports.functools_lru_cache 1.6.4              pyhd3eb1b0_0
backports.tempfile        1.0                pyhd3eb1b0_1
backports.weakref         1.0.post1                  py_1
beautifulsoup4            4.12.2          py311haa95532_0
blas                      1.0                         mkl
bleach                    4.1.0              pyhd3eb1b0_0
boltons                   23.0.0          py311haa95532_0
brotli                    1.0.9                h2bbff1b_7
brotli-bin                1.0.9                h2bbff1b_7
brotli-python             1.0.9           py311hd77b12b_7
bzip2                     1.0.8                he774522_0
ca-certificates           2023.08.22           haa95532_0
certifi                   2023.7.22       py311haa95532_0
cffi                      1.15.1          py311h2bbff1b_3
chardet                   4.0.0           py311haa95532_1003
charset-normalizer        2.0.4              pyhd3eb1b0_0
click                     8.1.7           py311haa95532_0
cloudpickle               2.2.1           py311haa95532_0
clyent                    1.2.2           py311haa95532_1
colorama                  0.4.6           py311haa95532_0
comm                      0.1.2           py311haa95532_0
conda                     23.10.0         py311haa95532_0
conda-build               3.26.1          py311haa95532_0
conda-content-trust       0.2.0           py311haa95532_0
conda-index               0.3.0           py311haa95532_0
conda-libmamba-solver     23.11.0         py311haa95532_0
conda-pack                0.6.0              pyhd3eb1b0_0
conda-package-handling    2.2.0           py311haa95532_0
conda-package-streaming   0.9.0           py311haa95532_0
conda-repo-cli            1.0.75          py311haa95532_0
conda-token               0.4.0              pyhd3eb1b0_0
conda-verify              3.4.2                      py_1
console_shortcut          0.1.1                         4
contourpy                 1.0.5           py311h59b6b97_0
cryptography              41.0.3          py311h89fc84f_0
cycler                    0.11.0             pyhd3eb1b0_0
dask-core                 2023.6.0        py311haa95532_0
debugpy                   1.6.7           py311hd77b12b_0
decorator                 5.1.1              pyhd3eb1b0_0
defusedxml                0.7.1              pyhd3eb1b0_0
entrypoints               0.4             py311haa95532_0
executing                 0.8.3              pyhd3eb1b0_0
filelock                  3.9.0           py311haa95532_0
fmt                       9.1.0                h6d14046_0
fonttools                 4.25.0             pyhd3eb1b0_0
freetype                  2.12.1               ha860e81_0
frozenlist                1.4.0           py311h2bbff1b_0
fsspec                    2023.9.2        py311haa95532_0
future                    0.18.3          py311haa95532_0
giflib                    5.2.1                h8cc25b3_3
glob2                     0.7                pyhd3eb1b0_0
icu                       73.1                 h6c2663c_0
idna                      3.4             py311haa95532_0
importlib-metadata        6.0.0           py311haa95532_0
importlib_metadata        6.0.0                hd3eb1b0_0
intake                    0.6.6           py311haa95532_0
intel-openmp              2023.1.0         h59b6b97_46320
ipykernel                 6.25.0          py311h746a85d_0
ipython                   8.15.0          py311haa95532_0
ipython_genutils          0.2.0              pyhd3eb1b0_1
jaraco.classes            3.2.1              pyhd3eb1b0_0
jedi                      0.18.1          py311haa95532_1
jinja2                    3.1.2           py311haa95532_0
joblib                    1.3.2                    pypi_0    pypi
jpeg                      9e                   h2bbff1b_1
jsonpatch                 1.32               pyhd3eb1b0_0
jsonpointer               2.1                pyhd3eb1b0_0
jsonschema                4.19.2          py311haa95532_0
jsonschema-specifications 2023.7.1        py311haa95532_0
jupyter_client            7.4.9           py311haa95532_0
jupyter_core              5.5.0           py311haa95532_0
jupyter_server            1.23.4          py311haa95532_0
jupyterlab_pygments       0.1.2                      py_0
keyring                   23.13.1         py311haa95532_0
kiwisolver                1.4.4           py311hd77b12b_0
krb5                      1.20.1               h5b6d351_0
lerc                      3.0                  hd77b12b_0
libarchive                3.6.2                hb62f4d4_2
libbrotlicommon           1.0.9                h2bbff1b_7
libbrotlidec              1.0.9                h2bbff1b_7
libbrotlienc              1.0.9                h2bbff1b_7
libclang                  14.0.6          default_hb5a9fac_1
libclang13                14.0.6          default_h8e68704_1
libcurl                   8.1.1                h86230a5_0
libdeflate                1.17                 h2bbff1b_1
libffi                    3.4.4                hd77b12b_0
libiconv                  1.16                 h2bbff1b_2
liblief                   0.12.3               hd77b12b_0
libmamba                  1.5.3                hcd6fe79_0
libmambapy                1.5.3           py311h77c03ed_0
libpng                    1.6.39               h8cc25b3_0
libpq                     12.15                h906ac69_1
libsodium                 1.0.18               h62dcd97_0
libsolv                   0.7.24               h23ce68f_0
libssh2                   1.10.0               he2ea4bf_2
libtiff                   4.5.1                hd77b12b_0
libwebp                   1.3.2                hbc33d0d_0
libwebp-base              1.3.2                h2bbff1b_0
libxml2                   2.10.4               h0ad7f3c_1
locket                    1.0.0           py311haa95532_0
lz4-c                     1.9.4                h2bbff1b_0
m2-msys2-runtime          2.5.0.17080.65c939c               3
m2-patch                  2.7.5                         2
markupsafe                2.1.1           py311h2bbff1b_0
matplotlib                3.8.0           py311haa95532_0
matplotlib-base           3.8.0           py311hf62ec03_0
matplotlib-inline         0.1.6           py311haa95532_0
menuinst                  1.4.19          py311h59b6b97_1
mistune                   2.0.4           py311haa95532_0
mkl                       2023.1.0         h6b88ed4_46358
mkl-service               2.4.0           py311h2bbff1b_1
mkl_fft                   1.3.8           py311h2bbff1b_0
mkl_random                1.2.4           py311h59b6b97_0
more-itertools            8.12.0             pyhd3eb1b0_0
msgpack-python            1.0.3           py311h59b6b97_0
msys2-conda-epoch         20160418                      1
multidict                 6.0.2           py311h2bbff1b_0
munkres                   1.1.4                      py_0
navigator-updater         0.4.0           py311haa95532_1
nbclassic                 1.0.0           py311haa95532_0
nbclient                  0.8.0           py311haa95532_0
nbconvert                 7.10.0          py311haa95532_0
nbformat                  5.9.2           py311haa95532_0
nest-asyncio              1.5.6           py311haa95532_0
networkx                  3.1             py311haa95532_0
nltk                      3.8.1                    pypi_0    pypi
notebook                  6.5.4           py311haa95532_1
notebook-shim             0.2.3           py311haa95532_0
numpy                     1.26.0          py311hdab7c0b_0
numpy-base                1.26.0          py311hd01c5d8_0
openjpeg                  2.4.0                h4fc8c34_0
openssl                   3.0.12               h2bbff1b_0
packaging                 23.1            py311haa95532_0
pandas                    2.1.4                    pypi_0    pypi
pandocfilters             1.5.0              pyhd3eb1b0_0
parso                     0.8.3              pyhd3eb1b0_0
partd                     1.4.1           py311haa95532_0
pathlib                   1.0.1              pyhd3eb1b0_1
pcre2                     10.42                h0ff8eda_0
pickleshare               0.7.5           pyhd3eb1b0_1003
pillow                    10.0.1          py311h045eedc_0
pip                       23.2.1          py311haa95532_0
pkce                      1.0.3           py311haa95532_0
pkginfo                   1.9.6           py311haa95532_0
platformdirs              3.10.0          py311haa95532_0
pluggy                    1.0.0           py311haa95532_1
ply                       3.11            py311haa95532_0
powershell_shortcut       0.0.1                         3
prometheus_client         0.14.1          py311haa95532_0
prompt-toolkit            3.0.36          py311haa95532_0
psutil                    5.9.0           py311h2bbff1b_0
pure_eval                 0.2.2              pyhd3eb1b0_0
py-lief                   0.12.3          py311hd77b12b_0
pybind11-abi              4                    hd3eb1b0_1
pycosat                   0.6.6           py311h2bbff1b_0
pycparser                 2.21               pyhd3eb1b0_0
pydantic                  1.10.12         py311h2bbff1b_1
pygments                  2.15.1          py311haa95532_1
pyjwt                     2.4.0           py311haa95532_0
pyopenssl                 23.2.0          py311haa95532_0
pyparsing                 3.0.9           py311haa95532_0
pyqt                      5.15.10         py311hd77b12b_0
pyqt5-sip                 12.13.0         py311h2bbff1b_0
pysocks                   1.7.1           py311haa95532_0
python                    3.11.5               he1021f5_0
python-dateutil           2.8.2              pyhd3eb1b0_0
python-dotenv             0.21.0          py311haa95532_0
python-fastjsonschema     2.16.2          py311haa95532_0
python-libarchive-c       2.9                pyhd3eb1b0_1
python-snappy             0.6.1           py311hd77b12b_0
pytz                      2023.3.post1    py311haa95532_0
pywin32                   305             py311h2bbff1b_0
pywin32-ctypes            0.2.0           py311haa95532_1000
pywinpty                  2.0.10          py311h5da7b33_0
pyyaml                    6.0.1           py311h2bbff1b_0
pyzmq                     23.2.0          py311hd77b12b_0
qt-main                   5.15.2              h19c9488_10
qtpy                      2.2.0           py311haa95532_0
referencing               0.30.2          py311haa95532_0
regex                     2023.12.25               pypi_0    pypi
reproc                    14.2.4               hd77b12b_1
reproc-cpp                14.2.4               hd77b12b_1
requests                  2.31.0          py311haa95532_0
requests-toolbelt         1.0.0           py311haa95532_0
rpds-py                   0.10.6          py311h062c2fa_0
ruamel.yaml               0.17.21         py311h2bbff1b_0
ruamel_yaml               0.17.21         py311h2bbff1b_0
scikit-learn              1.3.2                    pypi_0    pypi
scipy                     1.11.4                   pypi_0    pypi
seaborn                   0.13.1                   pypi_0    pypi
semver                    2.13.0             pyhd3eb1b0_0
send2trash                1.8.2           py311haa95532_0
setuptools                68.0.0          py311haa95532_0
sip                       6.7.12          py311hd77b12b_0
six                       1.16.0             pyhd3eb1b0_1
snappy                    1.1.9                h6c2663c_0
sniffio                   1.2.0           py311haa95532_1
soupsieve                 2.5             py311haa95532_0
sqlite                    3.41.2               h2bbff1b_0
stack_data                0.2.0              pyhd3eb1b0_0
tbb                       2021.8.0             h59b6b97_0
terminado                 0.17.1          py311haa95532_0
threadpoolctl             3.2.0                    pypi_0    pypi
tinycss2                  1.2.1           py311haa95532_0
tk                        8.6.12               h2bbff1b_0
toolz                     0.12.0          py311haa95532_0
tornado                   6.3.3           py311h2bbff1b_0
tqdm                      4.65.0          py311h746a85d_0
traitlets                 5.7.1           py311haa95532_0
truststore                0.8.0           py311haa95532_0
typing-extensions         4.7.1           py311haa95532_0
typing_extensions         4.7.1           py311haa95532_0
tzdata                    2023.4                   pypi_0    pypi
ujson                     5.4.0           py311hd77b12b_0
unicodedata2              15.1.0                   pypi_0    pypi
urllib3                   1.26.18         py311haa95532_0
vc                        14.2                 h21ff451_1
vs2015_runtime            14.27.29016          h5e58377_2
wcwidth                   0.2.5              pyhd3eb1b0_0
webencodings              0.5.1           py311haa95532_1
websocket-client          0.58.0          py311haa95532_4
wheel                     0.38.4          py311haa95532_0
win_inet_pton             1.1.0           py311haa95532_0
winpty                    0.4.3                         4
xz                        5.4.2                h8cc25b3_0
yaml                      0.2.5                he774522_0
yaml-cpp                  0.8.0                hd77b12b_0
yarl                      1.8.1           py311h2bbff1b_0
zeromq                    4.3.4                hd77b12b_0
zipp                      3.11.0          py311haa95532_0
zlib                      1.2.13               h8cc25b3_0
zstandard                 0.19.0          py311h2bbff1b_0
zstd                      1.5.5                hd43e919_0
```

##  **Experimental Design**
We applied the previously mentioned models to our dataset, in order to evaluate which one would be more useful. The criterion that was choosen for this was a specific metric: the F1 score. The reason why this is the best option is because it combines precision and recall, giving a good representation of the performance of the model for this binary classification task. Particularly, we wanted to avoid non-spam messages from being classified as spam, while also making it so that fraudolent texts do not reach the average unexperienced user. We also take a look at the accuracy of each model.

## **Results**
Considering what we have said until this point, we believe that the best model for our task is the Logistic Regression model (see picture in the images folder). The main reasons that led us to this decision can be summed up as follows:

*   While the model is quite overfitting - as we can see by looking at the performance on the Training set - the accuracy obtained on the Test set is incredibly good.

*   After tuning the C parameter, we obtain very good results on the classification task, with a number of false positives equal to 0 and just 10 false negatives. This is the best outcome that we obtain across all the models that we have taken into consideration.

*   Additionally, the F1 score, which was the main discriminant for this analysis, is very high.

## **Conclusions**

While our work tries to obtain the best results considered the task that was initially given, there is still a margin of improvement. In fact, our solution is only capable of performing a first basic classification process, which could still be improved for the sake of the final user. We believe that the next logic step would be to take into consideration the most dangerous type of fraudolent messages, particularly those that contain phone numbers or links, which could be used to extract private and sensitive information to the receiver. What should be done is to prioritize the analysis of text messages that include this type of flags, making it so that this specific type of messages do not end up becoming false negatives, ever. While our code does not actually define these *dangerous messages*, we still believe that this is a matter that should be addressed in the future.
