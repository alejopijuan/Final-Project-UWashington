
# coding: utf-8

# In[1]:

import graphlab


# In[28]:

train_image = graphlab.SFrame('image_train_data/')
test_image = graphlab.SFrame('image_test_data/')
train_image


# In[4]:

train_image['label'].sketch_summary()


# In[6]:

car = train_image.filter_by('automobile', 'label')


# In[8]:

cat = train_image.filter_by('cat', 'label')
bird = train_image.filter_by('bird', 'label')
dog = train_image.filter_by('dog', 'label')


# In[10]:

cat_model = graphlab.nearest_neighbors.create(cat,
                                             features=['deep_features']
                                             ,label='id')


# In[11]:

car_model = graphlab.nearest_neighbors.create(car,
                                             features=['deep_features']
                                             ,label='id')
dog_model = graphlab.nearest_neighbors.create(dog,
                                             features=['deep_features']
                                             ,label='id')
bird_model = graphlab.nearest_neighbors.create(bird,
                                             features=['deep_features']
                                             ,label='id')


# In[17]:

cat_model.query(test_image[0:1])


# In[19]:

def get_images_from_ids(query_result):
    return train_image.filter_by(query_result['reference_label'], 'id')


# In[22]:

cat_neighbors = get_images_from_ids(cat_model.query(test_image[0:1]))


# In[23]:

cat_neighbors.show()


# In[31]:

dog_model.query(test_image[0:1])


# In[29]:

dog_neighbors = get_images_from_ids(dog_model.query(test_image[0:1]))


# In[30]:

dog_neighbors.show()


# In[32]:

car_test = test_image.filter_by('automobile', 'label')
cat_test = test_image.filter_by('cat', 'label')
dog_test = test_image.filter_by('dog', 'label')
bird_test = test_image.filter_by('bird', 'label')


# In[33]:

dog_cat_neighbors = cat_model.query(dog_test, k=1)
dog_car_neighbors = car_model.query(dog_test, k=1)
dog_bird_neighbors = bird_model.query(dog_test, k=1)
dog_dog_neighbors = dog_model.query(dog_test, k=1)


# In[35]:

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



# In[36]:

dog_cat_neighbors


# In[39]:

dog_distances = graphlab.SFrame({'dog-dog':dog_dog_neighbors['distance'],
                                'dog-cat':dog_cat_neighbors['distance'],
                                'dog-car':dog_car_neighbors['distance'],
                                'dog-bird':dog_bird_neighbors['distance']})


# In[40]:

dog_distances


# In[41]:

def is_dog_correct(row):
    if row['dog-dog']< row['dog-cat'] and row['dog-dog']< row['dog-car'] and row['dog-dog']< row['dog-bird']:
        return 1
    else:
        return 0


# In[43]:

dog_distances.apply(is_dog_correct).sum()


# In[ ]:



