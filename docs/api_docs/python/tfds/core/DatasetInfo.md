<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tfds.core.DatasetInfo" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="as_json"/>
<meta itemprop="property" content="as_proto"/>
<meta itemprop="property" content="citation"/>
<meta itemprop="property" content="description"/>
<meta itemprop="property" content="download_checksums"/>
<meta itemprop="property" content="features"/>
<meta itemprop="property" content="initialized"/>
<meta itemprop="property" content="name"/>
<meta itemprop="property" content="num_examples"/>
<meta itemprop="property" content="size_in_bytes"/>
<meta itemprop="property" content="splits"/>
<meta itemprop="property" content="supervised_keys"/>
<meta itemprop="property" content="urls"/>
<meta itemprop="property" content="version"/>
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="compute_dynamic_properties"/>
<meta itemprop="property" content="initialize_from_package_data"/>
<meta itemprop="property" content="read_from_directory"/>
<meta itemprop="property" content="write_to_directory"/>
</div>

# tfds.core.DatasetInfo

## Class `DatasetInfo`





Defined in [`core/dataset_info.py`](https://github.com/tensorflow/datasets/tree/master/tensorflow_datasets/core/dataset_info.py).

Information about a dataset.

`DatasetInfo` documents datasets, including its name, version, and features.
See the constructor arguments and properties for a full list.

Note: Not all fields are known on construction and may be updated later
by `compute_dynamic_properties`. For example, the number of examples in each
split is typically updated during data generation (i.e. on calling
`builder.download_and_prepare()`).

<h2 id="__init__"><code>__init__</code></h2>

``` python
__init__(
    builder,
    description=None,
    features=None,
    supervised_keys=None,
    splits=None,
    urls=None,
    download_checksums=None,
    size_in_bytes=0,
    citation=None
)
```

Constructs DatasetInfo.

#### Args:

* <b>`builder`</b>: `DatasetBuilder`, dataset builder for this info.
* <b>`description`</b>: `str`, description of this dataset.
* <b>`features`</b>: <a href="../../tfds/features/FeaturesDict.md"><code>tfds.features.FeaturesDict</code></a>, Information on the feature dict
    of the `tf.data.Dataset()` object from the `builder.as_dataset()`
    method.
* <b>`supervised_keys`</b>: `tuple`, Specifies the input feature and the label for
    supervised learning, if applicable for the dataset.
* <b>`splits`</b>: <a href="../../tfds/core/SplitDict.md"><code>tfds.core.SplitDict</code></a>, the available splits for this dataset.
* <b>`urls`</b>: `list(str)`, optional, the homepage(s) for this dataset.
* <b>`download_checksums`</b>: `dict<str url, str sha256>`, URL to sha256 of file.
    If a url is not listed, its checksum is not checked.
* <b>`size_in_bytes`</b>: `int`, optional, approximate size in bytes of the raw
    size of the dataset that we will be downloading from the internet.
* <b>`citation`</b>: `str`, optional, the citation to use for this dataset.



## Properties

<h3 id="as_json"><code>as_json</code></h3>



<h3 id="as_proto"><code>as_proto</code></h3>



<h3 id="citation"><code>citation</code></h3>



<h3 id="description"><code>description</code></h3>



<h3 id="download_checksums"><code>download_checksums</code></h3>



<h3 id="features"><code>features</code></h3>



<h3 id="initialized"><code>initialized</code></h3>

Whether DatasetInfo has been fully initialized.

<h3 id="name"><code>name</code></h3>



<h3 id="num_examples"><code>num_examples</code></h3>



<h3 id="size_in_bytes"><code>size_in_bytes</code></h3>



<h3 id="splits"><code>splits</code></h3>



<h3 id="supervised_keys"><code>supervised_keys</code></h3>



<h3 id="urls"><code>urls</code></h3>



<h3 id="version"><code>version</code></h3>





## Methods

<h3 id="compute_dynamic_properties"><code>compute_dynamic_properties</code></h3>

``` python
compute_dynamic_properties()
```



<h3 id="initialize_from_package_data"><code>initialize_from_package_data</code></h3>

``` python
initialize_from_package_data()
```

Initialize DatasetInfo from package data, returns True on success.

<h3 id="read_from_directory"><code>read_from_directory</code></h3>

``` python
read_from_directory(
    dataset_info_dir,
    from_packaged_data=False
)
```

Update DatasetInfo from the JSON file in `dataset_info_dir`.

This function updates all the dynamically generated fields (num_examples,
hash, time of creation,...) of the DatasetInfo.

This will overwrite all previous metadata.

#### Args:

* <b>`dataset_info_dir`</b>: `str` The directory containing the metadata file. This
    should be the root directory of a specific dataset version.
* <b>`from_packaged_data`</b>: `bool`, If data is restored from packaged data,
    then only the informations not defined in the code are updated


#### Returns:

True if we were able to initialize using `dataset_info_dir`, else false.

<h3 id="write_to_directory"><code>write_to_directory</code></h3>

``` python
write_to_directory(dataset_info_dir)
```

Write `DatasetInfo` as JSON to `dataset_info_dir`.



