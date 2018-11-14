

```python
import graphlab
```


```python
train_image = graphlab.SFrame('image_train_data/')
test_image = graphlab.SFrame('image_test_data/')
train_image
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;"><table frame="box" rules="cols">
    <tr>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">id</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">image</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">label</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">deep_features</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">image_array</th>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">24</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Height: 32 Width: 32</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">bird</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[0.242871761322,<br>1.09545373917, 0.0, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[73.0, 77.0, 58.0, 71.0,<br>68.0, 50.0, 77.0, 69.0, ...</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">33</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Height: 32 Width: 32</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">cat</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[0.525087952614, 0.0,<br>0.0, 0.0, 0.0, 0.0, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[7.0, 5.0, 8.0, 7.0, 5.0,<br>8.0, 5.0, 4.0, 6.0, 7.0, ...</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">36</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Height: 32 Width: 32</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">cat</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[0.566015958786, 0.0,<br>0.0, 0.0, 0.0, 0.0, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[169.0, 122.0, 65.0,<br>131.0, 108.0, 75.0, ...</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">70</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Height: 32 Width: 32</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">dog</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[1.12979578972, 0.0, 0.0,<br>0.778194487095, 0.0, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[154.0, 179.0, 152.0,<br>159.0, 183.0, 157.0, ...</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">90</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Height: 32 Width: 32</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">bird</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[1.71786928177, 0.0, 0.0,<br>0.0, 0.0, 0.0, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[216.0, 195.0, 180.0,<br>201.0, 178.0, 160.0, ...</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">97</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Height: 32 Width: 32</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">automobile</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[1.57818555832, 0.0, 0.0,<br>0.0, 0.0, 0.0, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[33.0, 44.0, 27.0, 29.0,<br>44.0, 31.0, 32.0, 45.0, ...</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">107</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Height: 32 Width: 32</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">dog</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[0.0, 0.0,<br>0.220677852631, 0.0,  ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[97.0, 51.0, 31.0, 104.0,<br>58.0, 38.0, 107.0, 61.0, ...</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">121</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Height: 32 Width: 32</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">bird</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[0.0, 0.23753464222, 0.0,<br>0.0, 0.0, 0.0, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[93.0, 96.0, 88.0, 102.0,<br>106.0, 97.0, 117.0, ...</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">136</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Height: 32 Width: 32</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">automobile</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[0.0, 0.0, 0.0, 0.0, 0.0,<br>0.0, 7.5737862587, 0.0, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[35.0, 59.0, 53.0, 36.0,<br>56.0, 56.0, 42.0, 62.0, ...</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">138</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">Height: 32 Width: 32</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">bird</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[0.658935725689, 0.0,<br>0.0, 0.0, 0.0, 0.0, ...</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">[205.0, 193.0, 195.0,<br>200.0, 187.0, 193.0, ...</td>
    </tr>
</table>
[2005 rows x 5 columns]<br/>Note: Only the head of the SFrame is printed.<br/>You can use print_rows(num_rows=m, num_columns=n) to print more rows and columns.
</div>




```python
train_image['label'].sketch_summary()
```




    
    +------------------+-------+----------+
    |       item       | value | is exact |
    +------------------+-------+----------+
    |      Length      |  2005 |   Yes    |
    | # Missing Values |   0   |   Yes    |
    | # unique values  |   4   |    No    |
    +------------------+-------+----------+
    
    Most frequent items:
    +-------+------------+-----+-----+------+
    | value | automobile | cat | dog | bird |
    +-------+------------+-----+-----+------+
    | count |    509     | 509 | 509 | 478  |
    +-------+------------+-----+-----+------+





```python
car = train_image.filter_by('automobile', 'label')
```


```python
cat = train_image.filter_by('cat', 'label')
bird = train_image.filter_by('bird', 'label')
dog = train_image.filter_by('dog', 'label')
```


```python
cat_model = graphlab.nearest_neighbors.create(cat,
                                             features=['deep_features']
                                             ,label='id')
```


<pre>Starting brute force nearest neighbors model training.</pre>



```python
car_model = graphlab.nearest_neighbors.create(car,
                                             features=['deep_features']
                                             ,label='id')
dog_model = graphlab.nearest_neighbors.create(dog,
                                             features=['deep_features']
                                             ,label='id')
bird_model = graphlab.nearest_neighbors.create(bird,
                                             features=['deep_features']
                                             ,label='id')
```


<pre>Starting brute force nearest neighbors model training.</pre>



<pre>Starting brute force nearest neighbors model training.</pre>



<pre>Starting brute force nearest neighbors model training.</pre>



```python
cat_model.query(test_image[0:1])
```


<pre>Starting pairwise querying.</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 0            | 1       | 0.196464    | 16.774ms     |</pre>



<pre>| Done         |         | 100         | 117.564ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>





<div style="max-height:1000px;max-width:1500px;overflow:auto;"><table frame="box" rules="cols">
    <tr>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">query_label</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">reference_label</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">distance</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">rank</th>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">16289</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">34.623719208</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">45646</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">36.0068799284</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">2</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">32139</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">36.5200813436</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">3</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">25713</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">36.7548502521</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">4</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">331</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">36.8731228168</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5</td>
    </tr>
</table>
[5 rows x 4 columns]<br/>
</div>




```python
def get_images_from_ids(query_result):
    return train_image.filter_by(query_result['reference_label'], 'id')
```


```python
cat_neighbors = get_images_from_ids(cat_model.query(test_image[0:1]))
```


<pre>Starting pairwise querying.</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 0            | 1       | 0.196464    | 20.133ms     |</pre>



<pre>| Done         |         | 100         | 129.521ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



```python
cat_neighbors.show()
```

    Canvas is accessible via web browser at the URL: http://localhost:6897/index.html
    Opening Canvas in default web browser.



```python
dog_model.query(test_image[0:1])
```


<pre>Starting pairwise querying.</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 0            | 1       | 0.196464    | 15.044ms     |</pre>



<pre>| Done         |         | 100         | 101.27ms     |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>





<div style="max-height:1000px;max-width:1500px;overflow:auto;"><table frame="box" rules="cols">
    <tr>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">query_label</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">reference_label</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">distance</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">rank</th>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">16976</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">37.4642628784</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">13387</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">37.5666832169</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">2</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">35867</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">37.6047267079</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">3</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">44603</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">37.7065585153</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">4</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">6094</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">38.5113254907</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5</td>
    </tr>
</table>
[5 rows x 4 columns]<br/>
</div>




```python
dog_neighbors = get_images_from_ids(dog_model.query(test_image[0:1]))
```


<pre>Starting pairwise querying.</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 0            | 1       | 0.196464    | 13.034ms     |</pre>



<pre>| Done         |         | 100         | 115.306ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



```python
dog_neighbors.show()
```

    Canvas is accessible via web browser at the URL: http://localhost:6897/index.html
    Opening Canvas in default web browser.



```python
car_test = test_image.filter_by('automobile', 'label')
cat_test = test_image.filter_by('cat', 'label')
dog_test = test_image.filter_by('dog', 'label')
bird_test = test_image.filter_by('bird', 'label')
```


```python
dog_cat_neighbors = cat_model.query(dog_test, k=1)
dog_car_neighbors = car_model.query(dog_test, k=1)
dog_bird_neighbors = bird_model.query(dog_test, k=1)
dog_dog_neighbors = dog_model.query(dog_test, k=1)
```


<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 545.453ms    |</pre>



<pre>| Done         | 509000  | 100         | 585.562ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 452.203ms    |</pre>



<pre>| Done         | 509000  | 100         | 482.281ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 119000  | 24.8954     | 462.233ms    |</pre>



<pre>| Done         | 478000  | 100         | 485.291ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 471.255ms    |</pre>



<pre>| Done         | 509000  | 100         | 496.319ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



```python
cat_dog_neighbors = dog_model.query(cat_test, k=1)
cat_car_neighbors = car_model.query(cat_test, k=1)
cat_bird_neighbors = bird_model.query(cat_test, k=1)
cat_cat_neighbors = cat_model.query(cat_test, k=1)
car_dog_neighbors = dog_model.query(car_test, k=1)
car_cat_neighbors = cat_model.query(car_test, k=1)
car_bird_neighbors = bird_model.query(car_test, k=1)
car_car_neighbors = car_model.query(car_test, k=1)
bird_dog_neighbors = dog_model.query(bird_test, k=1)
bird_cat_neighbors = cat_model.query(bird_test, k=1)
bird_car_neighbors = car_model.query(bird_test, k=1)
bird_bird_neighbors = bird_model.query(bird_test, k=1)


```


<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 487.298ms    |</pre>



<pre>| Done         | 509000  | 100         | 525.397ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 519.383ms    |</pre>



<pre>| Done         | 509000  | 100         | 548.46ms     |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 120000  | 25.1046     | 463.234ms    |</pre>



<pre>| Done         | 478000  | 100         | 503.339ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 497.329ms    |</pre>



<pre>| Done         | 509000  | 100         | 549.46ms     |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 484.29ms     |</pre>



<pre>| Done         | 509000  | 100         | 531.412ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 504.359ms    |</pre>



<pre>| Done         | 509000  | 100         | 557.479ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 119000  | 24.8954     | 482.283ms    |</pre>



<pre>| Done         | 478000  | 100         | 500.33ms     |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 422.127ms    |</pre>



<pre>| Done         | 509000  | 100         | 475.262ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 481.28ms     |</pre>



<pre>| Done         | 509000  | 100         | 533.418ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 464.239ms    |</pre>



<pre>| Done         | 509000  | 100         | 518.379ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 127000  | 24.9509     | 458.221ms    |</pre>



<pre>| Done         | 509000  | 100         | 502.335ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>Starting blockwise querying.</pre>



<pre>max rows per data block: 4348</pre>



<pre>number of reference data blocks: 4</pre>



<pre>number of query data blocks: 1</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| Query points | # Pairs | % Complete. | Elapsed Time |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



<pre>| 1000         | 120000  | 25.1046     | 403.075ms    |</pre>



<pre>| Done         | 478000  | 100         | 434.156ms    |</pre>



<pre>+--------------+---------+-------------+--------------+</pre>



```python
dog_cat_neighbors
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;"><table frame="box" rules="cols">
    <tr>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">query_label</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">reference_label</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">distance</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">rank</th>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">0</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">33</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">36.4196077068</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">30606</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">38.8353268874</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">2</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5545</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">36.9763410854</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">3</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">19631</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">34.5750072914</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">4</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">7493</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">34.778824791</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">5</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">47044</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">35.1171578292</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">6</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">13918</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">40.6095830913</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">7</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">10981</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">39.9036867306</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">8</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">45456</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">38.0674700168</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">9</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">44673</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">42.7258732951</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">1</td>
    </tr>
</table>
[1000 rows x 4 columns]<br/>Note: Only the head of the SFrame is printed.<br/>You can use print_rows(num_rows=m, num_columns=n) to print more rows and columns.
</div>




```python
dog_distances = graphlab.SFrame({'dog-dog':dog_dog_neighbors['distance'],
                                'dog-cat':dog_cat_neighbors['distance'],
                                'dog-car':dog_car_neighbors['distance'],
                                'dog-bird':dog_bird_neighbors['distance']})
```


```python
dog_distances
```




<div style="max-height:1000px;max-width:1500px;overflow:auto;"><table frame="box" rules="cols">
    <tr>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">dog-bird</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">dog-car</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">dog-cat</th>
        <th style="padding-left: 1em; padding-right: 1em; text-align: center">dog-dog</th>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">41.7538647304</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">41.9579761457</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">36.4196077068</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">33.4773590373</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">41.3382958925</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">46.0021331807</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">38.8353268874</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">32.8458495684</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">38.6157590853</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">42.9462290692</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">36.9763410854</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">35.0397073189</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">37.0892269954</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">41.6866060048</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">34.5750072914</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">33.9010327697</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">38.272288694</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">39.2269664935</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">34.778824791</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">37.4849250909</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">39.1462089236</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">40.5845117698</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">35.1171578292</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">34.945165344</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">40.523040106</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">45.1067352961</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">40.6095830913</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">39.0957278345</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">38.1947918393</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">41.3221140974</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">39.9036867306</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">37.7696131032</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">40.1567131661</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">41.8244654995</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">38.0674700168</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">35.1089144603</td>
    </tr>
    <tr>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">45.5597962603</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">45.4976929401</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">42.7258732951</td>
        <td style="padding-left: 1em; padding-right: 1em; text-align: center; vertical-align: top">43.2422832585</td>
    </tr>
</table>
[1000 rows x 4 columns]<br/>Note: Only the head of the SFrame is printed.<br/>You can use print_rows(num_rows=m, num_columns=n) to print more rows and columns.
</div>




```python
def is_dog_correct(row):
    if row['dog-dog']< row['dog-cat'] and row['dog-dog']< row['dog-car'] and row['dog-dog']< row['dog-bird']:
        return 1
    else:
        return 0
```


```python
dog_distances.apply(is_dog_correct).sum()
```




    678L




```python

```
