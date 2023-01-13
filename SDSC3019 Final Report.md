

Recommendation System on HKTVmall

Based on Image-based processing and Natural

Language Processing

Group 7

Yuen Ho Man

Chan Chak Yan Esmond

Abstract : This project aims to give an algorithm for the recommendation system of HKTVmall online shopping network.

We will focus on two aspects: Image-based processing of different products’ photos listed on shop and Natural Language

Processing of products’ descriptions and names. We are aimed at providing top 10 personalized recommendations in

improving customer experience.

1





**1. Introduction**

**1.1 Background**

Language Processing to provide top 10

personalized recommendations in improving

customer experience in HKTVmall.

Online shopping has been a skyrocketing trend

these years. It has developed quickly and

diversified, while HKTVmall is a great example

demonstrating how online shopping has developed

these days. According to YouGov’s ranking(2022),

HKTVMall became Hong Kong's most talked

about brand in 2021. Ranked above Octopus Card

and ViuTV. With $22 million daily average gross

merchandise volume, more than 1450000 rapid

users and 4900000 apps download volume per

month.

**1.3 Data Extraction**

With the help of HKTVmall api, we can obtain

various data, including product title, description,

review, image for further analysis.

**1.2 Motivation**

With the impact of COVID-19, HKTVmall has

become one of the popular online shopping sites in

a short time. As people are not willing to get out

and risk the chances of getting sick, online

shopping becomes their first choice. There are

different kinds of categories offered on HKTVmall,

such as personal care, supermarket and housewares

etc. People can order all kinds of things through

their mobile phones. HKTVmall then will prepare

their ordered products, pack them into boxes and

directly deliver them to their apartment or the store

chosen by the customer to wait for pick up. As it

has a variety of products for customers, they may

find it difficult to look for products that really suit

them. Taking hair shampoo as an example, there

may be a lot of selling points for different products.

Some may provide a good smell, claim to have

better cleaning effects or have a larger capacity.

Different customers may be concerned about

different things, so a recommendation system is

therefore important, it helps suggest them goods

based on their browsing history.

**2. Method**

We have selected two models in generating a

10-items recommendation list. The models are

Image-based Processing Model and Natural

Language Processing Model. Both of them will be

covered below. Based on different types of users,

we will use a distinct approach to determine their

target products for further analysis. For users who

have not completed any transaction, we will select

the highest visit-frequency item as target. For users

who have completed a transaction, we will select

the recently purchased product as target.

**2.1 Model 1: Image-based Processing Model**

For Image-based Processing Model, we will focus

on the image similarity on different products within

the same category. As stated above, a target product

is selected based on their attribute. We will obtain

the product’s main image as the target image.

While considering the excessive amount of

product. The designed product comparing

algorithm is below:

In this situation, attracting customers to order

becomes one of the most important things an

E-Commerce company should do. One of the

methods is to provide a personalized browsing

experience for each user. HKTVmall has a block

named “FEATURED FOR YOU” based on each

category, yet it is actually not based on customers’

preference but a paid advertisement provided by

clients. It may not be what customers are looking

for or suitable for them, it thus may not have a

great impact in boosting the sales. As customers are

easily attracted by products’ shape and description,

we therefore will be focusing on designing an

algorithm with Image-based processing and Natural

\1. Remove purchased item from compare list

2.Randomly select x% of the total product for

comparison.

(The value of x will be determined in model

evaluation)

3.Calculate the image similarity of target and

selected image.

4.Take the best image and insert it into the

recommendation list.

5.Restart from step 2 if the product is inserted.

According to the algorithm, we have chosen 5

Similarity Index and each will be contributing a

2





product to the recommendation list. The chosen

Similarity Indexes is below:

In the feature extracting process, we choose ‘jieba’,

a python library for performing word splitting to

Chinese text. The cut\_all mode is off for better

accuracy.

Similarity Index of Image-based Processing Model

1.Structural Similarity based on scikit-image

(SSIM)

Figure 2. Example of Product Description after Word Splitting

with Jieba

From the example above, the word splitting process

can divide words with high accuracy. With the

results shown above, the designed product

comparing algorithm is below:

2.Cosine similarity

\1. Remove purchased item from compare list

2.Randomly select x% of the total product for

comparison.

Where, A and B are non-zero vector

(The value of x will be determined in model

evaluation)

3.Bray-Curtis Distance

3.Calculate the image similarity of target and

selected image.

4.Take the best image and insert it into the

recommendation list.

5.Restart from step 2 if the product is inserted.

According to the algorithm, We selected two

methods in determining the similarity between two

texts. Because of the computational time, TF-IDF

will contribute 3 items to the list, while Word2vec

contributes 2 items. The methods detail is below:

Where, u and v are nonzero vector

4.Euclidean Distance

Where, x and y are two vectors

5.Jensen-Shannon Distance

Method of Natural Language Processing Model

1.Term Frequency–Inverse Document Frequency

(TF-IDF)

**2.2 Model 2: Natural Language Processing**

**Model**

For Natural Language Processing Model, we will

focus on the text similarity on different products.

We will extract the text feature given by product

name, description and review. Only Chinese text

will be considered as major customers are from

Hong Kong.

2.Word2vec

The method of Word2vec will be used in

performing word embeddings learning with neural

networks. It can change words to vectors in

predicting the probability that words will appear.

In the Word2vec algorithm, there are two models

including Skip Gram and Common Bag Of Words

(CBOW). According to T.Mikolov (2013), CBOW

Figure 1. Example of Product Description

3





is able to run faster than Skip Gram and has a better

representation of more frequent words. Referring to

the excessive amount of data in HKTVmall, we

decided to use CBOW as the method under

Word2vec.

**3.1 Model Evaluation : Image-based**

**Processing Model**

To evaluate the performance of an Image-based

Processing Model, computational time is an

important concern. In the category of women's

backpacks, there are a total of 2367 items. For the

computational time, we will test all the integer

values from 0 to 100 of x.

**2.3 Algorithm Formation**

The algorithm is designed based on a common

shopping habit. For the randomness part in both

algorithms. According to L.McAlister (1982), there

is a customer behavior named as variety seeking

behavior. For customers with this behavior, they

will seek for other products different from the one

they bought. The reason behind this behavior does

not mean they are not satisfied with the previous

product, it is that they prefer to seek variety.

However, refer to C.Wang (2010), there still a large

number of customers under Behavioral brand

loyalty which tend to buy the products in the same

brand.

Figure 3. Computational Time and Lowest MSE in Different

Value of x

From Figure 1, it illustrates the computational time

to different values of x. With calculating the

correlation between the time and lowest MSE:

Therefore, we want to simulate customers behavior

based on randomness, where the customers are

usually choosing random products different from

the product they bought, products which are in the

same brand or products based on their preference

which may be varied from time to time.

We can clearly see that there is a negative

relationship, where the higher computational time

refers to lower MSE. The P-value is statistically

significant.

For both algorithms, the value of x in the

randomness part will be evaluated in the next

section.

During the evaluation on the value of x, the lowest

MSE decreases when the value of x is around 25.

Therefore, for the Image-based Processing Model,

we decided the range of x should be between

25-50% for better accuracy and lower

computational time.

**3. Result**

With the two models above, we evaluate the model

in optimizing between the computational time and

accuracy. The Index of determining the accuracy is

the lowest mean-square error (MSE). For the

Evaluation part below, we select all products under

the

category

of

&

All

products<Women's

as

**3.2 Results : Image-based Processing Model**

We set x=30% for the example shown below. As

for the result of the algorithm, it will generate a

table with similarity index, index value, product ID,

product name, brand and image url.

Fashion<Bags

demonstration. In the category, there are a total of

2367 items.

Wallets<Backpacks

For the following conditions, it is given that a

customer bought THE LITTLE PRINCE SPECIAL

EDITION BACKPACK.

Figure 4. Table generated from image-based processing model

The following figures are the products from Figure

2 by order.

4





between 30-55% for better accuracy and lower

computational time.

**3.4 Results : Natural Language Processing**

**Model**

Figure 4.1

Figure 4.2

Figure 4.3

We set x=50% for the example shown below. As

for the result of the algorithm, it will generate a

table with similarity index, product ID, product

name, summary and review. The following figures

are the products from Figure 3 by order.

Figure 4.4

Figure 4.5

From the figures suggested, it is shown that they

have a similar shape with the purchased product

except Figure 4.4. It can be explained by

randomness that there is a chance the list may

include unrelated products.

Figure 6. Table generated from natural-language processing

model

The following figures are the products from Figure

2 by order.

**3.3 Model Evaluation : Natural Language**

**Processing Model**

Same as Image-based Processing, our target is to

get a balance between computational time and the

accuracy (measured by the lowest MSE). For the

computational time, we will test all the integer

values from 0 to 100 of x.

Figure 6.1

Figure 6.2

Figure 6.3

Figure 6.4

Figure 6.5

From the above figures, Figures 6.1 and 6.2 have

the same brand as the purchased one. While Figure

6.3 is also a special edition and Figure 6.4 is also

blue, these features are mentioned in the product

name of Figure 6. As for Figure 6.5, it is an

unrelated product like Figure 4.4 above.

Figure 5. Computational Time and Lowest MSE in Different

Value of x in NLP Model

**4. Discussion**

From Figure 2, it illustrates the computational time

to different values of x. With calculating the

correlation between the time and lowest MSE:

The recommendation list can show some important

features of the target image. With the Image-based

Processing Model, the list can suggest the product

based on the shape. With the Natural Language

Processing Model, the list obtains the product

based on the unique selling proposition. However,

for both models, there are some unrelated products

like Figure 4.4 from image-based processing model

and Figure 6.5 from natural-language processing

model. It is expected as the algorithm is based on

randomness.

We can clearly see that there is a negative

relationship, which is the same as the Image-based

Processing Model. The P-value is also statistically

significant. For the value of x, the lowest MSE

decreases when the value of x is around 30.

Therefore, for the Natural Language Processing

Model, we decided the range of x should be

5





**4.1 Limitation**

For limitation, the amount of products is way too

big that it may cost too much time to run the

process. We try to tackle it by extracting x% of the

total amount of products in the category and run

one of the methods. However, it still requires a long

time to process.

Another limit is that during the image processing,

they will be changed from BGR to grayscale. So

we will not be able to consider the color difference

as a reference.

**4.2 Recommendations for Future Research**

We are not able to figure out patterns of customers’

habits based on the data obtained, which affects the

accuracy a lot. Therefore, the suggestions may not

match their preference. It is recommended to

perform predictions on customers’ purchasing

habits into consideration in future research.

**4.3 Conclusion**

Recommendation system is an important

component as it should be able to predict the desire

of a user and suggest products matching the user’s

preference. Based on image-based processing and

natural language processing, we hope the system

can help customers to find suitable products and

stimulate sales. We believe a good recommendation

system will be able to help both customers and

HKTVmall.

**5. Appendix**

**5.1 Code example for Image-based Processing**

**Model**

6





2022,

https://zhuanlan.zhihu.com/p/28943718

Understanding TF-ID: simple

introduction. MonkeyLearn Blog. (2019,

May 10). Retrieved October 16, 2022,

from

https://monkeylearn.com/blog/what-is-tf-i

df/

Alake, R. (2021, November 3).

Understanding cosine similarity and its

application. Medium. Retrieved October

from

\3.

\4.

A

16,

2022,

from

https://towardsdatascience.com/understan

ding-cosine-similarity-and-its-application-

fd42f585296a

\5.

\6.

Building a Recommender System Using

Amazon Reviews. (2018, October 15).

Retrieved

November 3, 2022, from

https://github.com/smwitkowski/Amazon-

Recommender-System/blob/master/Collab

orative%20Filtering%20Amazon%20Watc

h%20Reviews.ipynb

Ben Chamblee. (2022, February 7). What

is Cosine Similarity? How to Compare

Text and Images in Python. Retrieved

**5.2 Code example for Natural Language**

**Processing Model**

November

3,

2022

from

https://towardsdatascience.com/what-is-co

sine-similarity-how-to-compare-text-and-i

mages-in-python-d2bb6e411ef0

\7.

\8.

scipy.spatial.distance.cdist.

Retrieved

(n.d.).

from

https://docs.scipy.org/doc/scipy/reference/

generated/scipy.spatial.distance.cdist.html

Adrian Rosebrock. (2015, March 2).

Convert URL to image with Python and

OpenCV. Retrieved November 3, 2022,

from

https://pyimagesearch.com/2015/03/02/co

nvert-url-to-image-with-python-and-openc

v/

\9.

\10.

\11.

scipy.spatial.distance.jensenshannon.

(n.d.).

Retrieved

from

https://docs.scipy.org/doc/scipy/reference/

generated/scipy.spatial.distance.jensensha

nnon.html

**6. Reference**

\1.

Baek,

J.

H.

(n.d.).

Amazon

scipy.spatial.distance.braycurtis.

Retrieved

(n.d.).

from

Recomzmender System. UC San Diego

Library | Digital Collections. Retrieved

October

https://library.ucsd.edu/dc/object/bb85037

44c

https://docs.scipy.org/doc/scipy/reference/

generated/scipy.spatial.distance.braycurtis.

html

Distributed representations of words and

phrases and their compositionality. (n.d.).

16,

2022,

from

\2.

一灯架构. (n.d.). Gensim word2vec 使用

教程. 知乎专栏. Retrieved October 16,

7





Retrieved December 1, 2022, from

https://arxiv.org/pdf/1310.4546.pdf

\12.

Karani, D. (2020, September 2).

Introduction to word embedding and

word2vec. Medium. Retrieved December

1,

2022,

from

https://towardsdatascience.com/introducti

on-to-word-embedding-and-word2vec-652

d0c2060fa

8

