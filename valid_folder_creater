import shutil, random, os
import os.path


train_folder = 'Downloads/train-2/'
valid_folder = train_folder+'valid/'

#get list of label directories inside train train_folder
subdir_ls = [item for item in os.listdir(train_folder) if os.path.isdir(os.path.join(train_folder, item))]

for subdir in subdir_ls:
    #get adress of each label folder
    dirpath = train_folder+subdir
    #create empty valid folder of this label
    destDirectory = os.makedirs(valid_folder+subdir, exist_ok=True)
    #get adress of created valid folder
    destDirectory = valid_folder+subdir
    
    #count how many images inside label folder
    subdir_numb = len([item for item in os.listdir(dirpath) if os.path.isfile(os.path.join(dirpath, item))])
    #count 20% of images above
    valid_numb = int(round(subdir_numb * .2, 0))
    
    #get 20% of label folder and create list
    filenames = random.sample(os.listdir(dirpath), valid_numb)
    
    #move each file of this 20% subset to valid folder for each label
    for fname in filenames:
        srcpath = os.path.join(dirpath, fname)
        shutil.move(srcpath, destDirectory)


    
