### **The last 50 instences in iris data is one type "Virginica" and also The first 50 instences is "setosa". so the rest data is just two classes**

* **The head 50 instences from data**

![](8.png)

* **The tail 50 instences from data**

![](9.png)



# Impelementation of Soft Margin SVM with Gradient Descent

## HyperPlane Equation
![](https://latex.codecogs.com/gif.latex?h%28x%29%3D%5Cbeta%5E%7BT%7D%20X&plus;b)

![](10.png)

## Cost Function or Loss Function (We try to Minimize this Function . to increase margin that help us to choose the best hyberPlane)
![](https://latex.codecogs.com/gif.latex?Loss%3D%5Cfrac%7B%5Cbeta%5E%7BT%7D%5Cbeta%7D%7B2%7D&plus;%20C%5Csum%7B%5Cepsilon_%7Bi%7D%7D)

* **Slack Variable : ![](https://latex.codecogs.com/gif.latex?%5Cepsilon_%7Bi%7D%20%3Dmax%280%2C1-y_%7Bi%7D%28%5Cbeta%5E%7BT%7DX_%7Bi%7D&plus;b%29%29)**

**Depend On**

![](https://latex.codecogs.com/gif.latex?y_%7Bi%7D%28%5Cbeta%5E%7BT%7DX_%7Bi%7D&plus;b%29%3E%3D1-%5Cepsilon_%7Bi%7D)

![](11.png)

> **HyperParameter C can determine margin if c close to zero so we trying maximize margin and vice verse**

## Margin
![](https://latex.codecogs.com/gif.latex?Margin%3Dy_%7Bi%7D%28%5Cbeta%5E%7BT%7DX_%7Bi%7D&plus;b%29)

**Where**

![](https://latex.codecogs.com/gif.latex?y_%7Bi%7D%28%5Cbeta%5E%7BT%7DX_%7Bi%7D&plus;b%29%20%5Cgeqslant%201%24%20in%20Canonical%20HyperPlane%20or%20in%20general%20%24y_%7Bi%7D%28%5Cbeta%5E%7BT%7DX_%7Bi%7D&plus;b%29%5Cgeqslant%20margin)

![](12.png)  

## Gradient Descent 
**as we learnt in the second lecture, We can update weightes by derivative of cost function w.r.t weights and learning rate or ![](https://latex.codecogs.com/gif.latex?%5Clambda)**


![](https://latex.codecogs.com/gif.latex?Loss%3D%5Cfrac%7B%5Cbeta%5E%7BT%7D%5Cbeta%7D%7B2%7D&plus;%20C%5Csum%7B%5Cepsilon_%7Bi%7D%7D)

**Derivative w.r.t Beta : ![](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%20Loss%7D%7B%5Cpartial%20%5Cbeta%7D%20%3D%5Cbeta%20-C%5Csum%7By_%7Bi%7Dx_%7Bi%7D%7D)**

**Update of beta :![](https://latex.codecogs.com/gif.latex?%5Cbeta%3D%5Cbeta-%5Clambda%20%5Cfrac%7B%5Cpartial%20Loss%7D%7B%5Cpartial%20%5Cbeta%7D)**

**Derivative w.r.t b : ![](https://latex.codecogs.com/gif.latex?%5Cfrac%7B%5Cpartial%20Loss%7D%7B%5Cpartial%20b%7D%20%3D%20-C%5Csum%7By_%7Bi%7D%7D)**

**Update of b :![](https://latex.codecogs.com/gif.latex?b%3Db-%5Clambda%20%5Cfrac%7B%5Cpartial%20Loss%7D%7B%5Cpartial%20b%7D)**

> For sure, We update weights based on missclassified points

![](13.png)

## Fitting Function 
**That return Support vectors where the maximum margin with the best hyperPlane is found**

![](14.png)

## Predict Function 
**That return only 1 if HyperPlaneequation > 0 or -1  if   HyperPlaneequation <0**

![](15.png)

## Score Function 
![](16.png)

## Load Data Function  
**I used the first 100 Instences from iris data**
**Split Data with 10% for testing data and 90% for training data**

![](17.png)

## Result

![](18.png)

> When I used the first 100 instences from iris data

![](19.png)

> when i used the last 100 instences from iris data


## All Data
**When I used all data not splitting it to train and test set. because data is very small,just 100 instences and plotting it, it was result**

> When i used the last 100 instences


![](20.png)

> When i used the first 100 instences


![](21.png)


# Conclusion

* **AS We saw in result section, Data with the first 100 instences is more better and without error so it svm with hard margin and we dont need port of slack variable becouse data in this case linearly seperable.** 

* **and with the the last 100 instences data isn't linearly seperable so I used soft margin svm** 

* **I implemented soft margin SVM for this data to be more effective with two part from data (the last and the first 100 instences)**