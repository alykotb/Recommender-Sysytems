
GET STARTED
===========
**Run in python environment installed on a machine**

If you are using a python environmnet running on your machine running the CF.py or CF.ipynb not in google-colab these libraries should be installed 
in your environment:

 1. torch
 2. pandas
 3. numpy
 4. pytorch_lightning
 5. torchmetrics 
 6. argparse (for CF.py only)
 7. sklearn
 8. random


Example to train the model and plot the loss locally in a command-line interpreter:

Run CF.py to train the model:
```
 python CF.py --epochs 20 --batch_size 256 
```

**Running the Jupyter notebook locally or using Google Colab**

This video - https://www.youtube.com/watch?v=hAvJN82ulg8 - explains how to upload your dataset file on your google drive
and access it in Google Colab.Then you can run the code normally in the Colab notebook.


You have to run all the cells in the notebook file. At the end there are two notebooks, the first one you will run and enter the required epochs
and bath-size to train the model and plot your loss.

Note-book for model-training:
```
ep = input("Enter the number of epochs:")
bs = input("Enter the batch-size:")
random.seed(0)
np.random.seed(0)
torch.manual_seed(0)

model = CollaborativeFiltering(num_users, num_movies, train_users, train_movies, train_labels, int(bs))

random.seed(0)
np.random.seed(0)
torch.manual_seed(0)

trainer = pl.Trainer(max_epochs=int(ep))
trainer.fit(model)
plot
```



**Calculating a recommendation list for a user**

Using CF.py in local environment:

- After running the model through the python command-line and the model finishes training the code will keep asking you to enter the
  user's id you want to find the top 5 recommenadtion list for a user and whenever it displays a user's list it will ask for the following
  user. 

Example:

```
Enter the user's id:1
Movies recommendation list:
Movie's id:1649
Movie's id:2190
Movie's id:2613
Movie's id:1226
Movie's id:764
Enter the user's id:2
```



Jupyter or Colab notebook:

The last cell in the note-book is to find the top-5 recommended movies for your input user:
```
user = input("Enter the user's id:")
get_user_pred_list(int(user)-1)
```
