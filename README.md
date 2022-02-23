# Wordcloud
import numpy as np
import pandas as pd
df=pd.read_csv("D:\document\\TinderSwindlerVersion2.csv")
df.head(100)
df.source.value_counts()
df.isnull().sum()
df.shape
df1=df.dropna(subset=['user_location'])
df1.shape
import matplotlib.pyplot as plt
import seaborn as sns
plt.figure(figsize=(15,10))
sns.set(style="darkgrid")
ax= sns.countplot(y="user_location",data=df1,order=df1['user_location'].value_counts().index[0:25])
df1.text.value_counts
from wordcloud import WordCloud
reader_ob=df1['text']
reader_contents= list(reader_ob)
reader_contents
text=""
for row in reader_contents:
    for word in row :
        text = text+""+ word
#wordcloud image object for generating and grawng
wordcloud=WordCloud(width=900,height=600, max_words=90,mode='RGBA',background_color='black').generate(text) 
plt.figure()# plot the wordcloudimage 
plt.imshow(wordcloud, interpolation="bilinear") 
plt.axis("off")
plt.margins(x=0,y=-0.25)
plt.show()
plt.figure(figsize=(15,10))
sns.set(style="darkgrid")
ax=sns.countplot(x="source",data=df1,order=df1["source"].value_counts().index[0:5])
