# Mask_R-CNN
Mask R-CNN Code Examples

*Note: Some packages may need to be installed from conda-forge. Make sure conda-forge is added as a package source.* Edit *.condarc* to add *conda-forge* after *defaults*. It should look like this:
- defaults
- conda-forge

# Configure Anaconda Environment
    conda create --name maskrcnn python=3.6
    conda activate maskrcnn
    conda install numpy     # to link it with Intel's MKL library for increased numpy performance
    
**Create a project folder and *cd* into it.**

    mkdir myproject && cd myproject

**Clone the [Mask R-CNN repo](https://github.com/matterport/Mask_RCNN) and *cd* into it.**

      git clone https://github.com/matterport/Mask_RCNN.git && cd Mask_RCNN

**Replace the contents of the existing *requirements.txt* file with the content below:**

    scipy==1.4.1
    Pillow
    cython
    matplotlib
    scikit-image==0.16.2
    keras==2.1.3
    tensorflow-gpu==1.15.4
    h5py
    imgaug
    IPython[all]
    jupyter
    
 **Install the requirements with pip, not with conda:**
 
    pip3 install -r requirements.txt  # the file in this repo

Compared to the original requirements in the [Matterport Mask R-CNN repo](https://github.com/matterport/Mask_RCNN), the *new* requirements file has the following changes:

*Excludes the following:*

- numpy (it was installed manually in the previous step) 

*Other changes:*

- sets tensorflow to tensorflow-gpu==1.15.2
- scikit-image==0.16.2 to generate less warnings at training
- sets scipy==1.4.1 to be compatible with TF 1.15.2
- sets keras==2.1.3 to be compatible with TF 1.15.2 and to train on multiple GPUs
- installs jupyter

**Run the following:**
      
      python3 setup.py install
      
**Download the pre-trained model weights trained on the [COCO dataset](https://cocodataset.org/)**

    wget https://github.com/matterport/Mask_RCNN/releases/download/v1.0/mask_rcnn_coco.h5

**Clone the [cocoapi repo](https://github.com/cocodataset/cocoapi) make and istall the Python API.**

    git clone https://github.com/cocodataset/cocoapi.git && cd cocoapi/PythonAPI/ && make && make install && cd ../../
