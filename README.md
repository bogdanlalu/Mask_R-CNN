# Mask_R-CNN
Mask R-CNN Code Examples

*Note: Some packages need to be installed from conda-forge (i.e. opencv). Make sure conda-forge is added as a package source.* Edit *.condarc* to add *conda-forge* after *defaults*. It should look like this:
- defaults
- conda-forge

# Configure Anaconda Environment
    conda create --name maskrcnn python=3.6
    conda activate maskrcnn
    conda install numpy     # to make sure it installs Intel's MKL library
    conda install --file requirements2.txt

Compared to the original requirements in the [Mask R-CNN repo](https://github.com/matterport/Mask_RCNN), requirements2.txt has the following changes:

**Excludes the following:**
- numpy (it was installed manually) 
- TensorFlow (Version 1.15.2 will be installed manually with pip - it's not available through the 2 conda channels.)
- opencv-python (doesn't look like it's needed, it will be installed by conda as a dependency to one of the packages in requirements2.txt)

**Other changes:**
- sets scipy==1.4.1 to be compatible with TF 1.5
- sets keras==2.3.1 to be compatible with TF 1.5
- installs jupyter

      pip3 install tensorflow==1.15.2 (Do not install 1.15.0 as it has a security flaw)
- Create a project folder and *cd* into it
- Now clone the [Mask R-CNN repo](https://github.com/matterport/Mask_RCNN)

      git clone https://github.com/matterport/Mask_RCNN.git
      cd Mask_RCNN
      python3 setup.py install
Download the pre-trained model weights trained on the [COCO dataset](https://cocodataset.org/)

    wget https://github.com/matterport/Mask_RCNN/releases/download/v1.0/mask_rcnn_coco.h5

Clone the [cocoapi repo](https://github.com/cocodataset/cocoapi) (we're still in the Mask_RCNN folder). Navigate to the coco PythonAPI, make and istall.

    git clone https://github.com/cocodataset/cocoapi.git
    cd cocoapi/PythonAPI/
    make
    make install
    cd ../../
