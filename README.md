# Mask_R-CNN
Mask R-CNN Code Examples

*Note: Some packages may need to be installed from conda-forge. Make sure conda-forge is added as a package source.* Edit *.condarc* to add *conda-forge* after *defaults*. It should look like this:
- defaults
- conda-forge

# Configure Anaconda Environment
    conda create --name maskrcnn python=3.6
    conda activate maskrcnn
    conda install numpy     # to link it with Intel's MKL library for increased numpy performance
    
Create a project folder and *cd* into it.

    mkdir myproject && cd myproject

Now clone the [Mask R-CNN repo](https://github.com/matterport/Mask_RCNN) and *cd* into it.

      git clone https://github.com/matterport/Mask_RCNN.git && cd Mask_RCNN

Replace the contents of the existing *requirements.txt* file with the content below:

    scipy==1.4.1
    Pillow
    cython
    matplotlib
    scikit-image
    keras==2.2.5
    tensorflow==1.15.2
    h5py
    imgaug
    IPython[all]
    jupyter
    
 Then install the requirements with pip, not with conda:
 
    pip3 install -r requirements_new.txt  # the file in this repo

Compared to the original requirements in the [Matterport Mask R-CNN repo](https://github.com/matterport/Mask_RCNN), *requirements_new.txt* has the following changes:

**Excludes the following:**

- numpy (it was installed manually in the previous step) 

**Other changes:**

- sets tensorflow==1.15.2
- sets scipy==1.4.1 to be compatible with TF 1.15.2
- sets keras==2.2.5 to be compatible with TF 1.15.2
- installs jupyter

Run the following:
      
      python3 setup.py install
      
Download the pre-trained model weights trained on the [COCO dataset](https://cocodataset.org/)

    wget https://github.com/matterport/Mask_RCNN/releases/download/v1.0/mask_rcnn_coco.h5

Clone the [cocoapi repo](https://github.com/cocodataset/cocoapi) (we're still in the Mask_RCNN folder). Navigate to the coco PythonAPI, make and istall.

    git clone https://github.com/cocodataset/cocoapi.git && cd cocoapi/PythonAPI/ && make && make install && cd ../../
