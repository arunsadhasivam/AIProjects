
https://pytorch.org/ - it is like spring.io. select framework needed and click download
pip3 install torch torchvision torchaudio


to install as zip:
===================

step 1:
========

 Anaconda is a distribution manager install that so you can create a environment it 
 automatically install all depend 

https://repo.anaconda.com/archive/.winzip/

Step 2:
=======

install pycharm community edition.
 
 https://www.jetbrains.com/pycharm/download/other.html

Step 3(manually create virtual env):
===================================

create virtual env.

to list environment:
=====================
C:\MachineLearning\Anaconda3\condabin>conda env list
      # conda environments:
      #
      base                     C:\MachineLearning\Anaconda3


NOTE:
-----

never work on base , create a environment for specific requirement like for e.g i create env pytorch to
work on pytorch project

C:\MachineLearning\Anaconda3\condabin>conda create --name pytorch
Collecting package metadata (current_repodata.json): done
Solving environment: done

step 4(through pytorch):
=============================


![image](https://github.com/user-attachments/assets/cb5f5c24-1cc5-442d-9afb-1a0e60dc9819)


C:\MachineLearning\pytorchvenv - is like library folder in java. you can specify whethre reuse 
this virutal env for other project. so that no need to install again and again.
C:\MachineLearning\Workspace\PytorchProj - path where pytorch PytorchProj  saved

Step 5:
=======
once project created you can use virutal env ( pytorchenv) gets added to C:\MachineLearning\Workspace\PytorchProj
it is almost like create **new user library**  and reuse for other project in eclipse.
![image](https://github.com/user-attachments/assets/ea549d1f-e796-4ef5-bf30-7d066190dcf6)

Step 6:
=======
to activate env

  (pytorchvenv) PS C:\MachineLearning\pytorchvenv\Scripts> ./activate.ps1

![image](https://github.com/user-attachments/assets/f75c4af1-ee9d-49d3-bba1-f001d680dc56)

NOTE:
=====

./activate.ps1 because (powershell)
