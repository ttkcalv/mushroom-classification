# mushroom-classification
Classification of mushrooms' edibility by their physical characteristics
### Project Scenario

You're thinking of going on a hike through the forest.

You enjoy mushrooms a lot, and anticipate them appearing as you traverse the woods. The problem with mushrooms is that while many are edible, there are those among them that are highly poisonous.

Fortunately, you remember that there's a field guide containing mushroom information; you decide to train a model to tell you whether the mushrooms you encounter are poisonous.

### What we'll be doing:
In this project, we will do the following:

1. Download mushroom field guide data and clean the data up (Part I)
2. Perform exploratory data analysis (Part II)
3. Apply machine learning techniques to train a model to predict mushroom edibility (Part III and IV)

### Dataset
We'll be getting our data from the <a href='https://archive.ics.uci.edu/ml/datasets/Mushroom'>UCI Machine Learning Repository</a>. 

More specifically, the data is submitted by the Audobon Society Field Guide, a nature reference. 

Download the data <a href = 'https://archive.ics.uci.edu/ml/machine-learning-databases/mushroom/'>here</a>. We will need only two files:
1. agarious-lepiota.data
2. agarious-lepiota.names

### Inspecting the data definitions
From `agarious-lepiota.data` we first learn that the columns in the dataset are as below:
        ![image](https://user-images.githubusercontent.com/101868958/185567281-edb7a7e0-8110-497a-afd1-2f52f8de9e97.png)

With that in mind, we can now proceed to import and clean our dataset.

### Part I: Data Preparation
Having understood the data definitions the `Mushroom Classification Part 1 - Data Preparation` notebook takes us through providing the proper column names for our data.

i.e. From this:

![image](https://user-images.githubusercontent.com/101868958/185568339-805c584f-780b-465f-afed-af9b445e2daf.png)

To this:

![image](https://user-images.githubusercontent.com/101868958/185568524-ad6f5232-9604-4dfc-a8de-53cec1cfc519.png)

### Part II: Exploratory Data Analysis
We'll use Seaborn to do an initial exploration of the data in our dataset.
The initial exploration of our dataset yielded the following findings:
![image](https://user-images.githubusercontent.com/101868958/185568766-fe07f6b4-28f4-4612-9982-b6b1df016cd1.png)

From the countplot, it seems that at least for the mushrooms included in this dataset, there is a fairly even distribution of edible and poisonous mushrooms, with edible mushrooms edging out poisonous mushrooms slightly.

![image](https://user-images.githubusercontent.com/101868958/185569072-65b49731-947a-4e12-9f1f-9a02a874f38f.png)

The most common cap_shape for mushrooms in this data set is x (convex), followed by f (flat) and k (knobbed).

![image](https://user-images.githubusercontent.com/101868958/185569193-30c75197-2b71-4f50-b95d-343e219a5a66.png)

Perhaps most importantly, when plotting the countplot of mushrooms by 'cap_shape' and with 'class' as hue, we observe that:
1. There are more edible mushrooms with b cap shape (bell) than poisonous ones
2. There are no poisonous mushrooms with s cap shape (sunken)

![image](https://user-images.githubusercontent.com/101868958/185569580-8bdf6f59-073d-4d47-9b71-dcd529f5a792.png)

Finally, we also make an interesting observation involving the odor of mushrooms:
Odorless (n) mushrooms have a very high chance of being edible, so in a desperate situation, looking for odorless mushrooms might be one's best bet.
