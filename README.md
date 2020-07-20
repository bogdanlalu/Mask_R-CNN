# Mask_R-CNN
Mask R-CNN Code Examples

# Configure Anaconda Env
    conda create --name maskrcnn python=3.6
    conda activate maskrcnn
    conda install numpy     # to make sure it installs Intel's MKL library
    conda install --file requirements2.txt

Compared to the original requirements in the [Mask R-CNN repo](https://github.com/matterport/Mask_RCNN), requirements2.txt has the folling changes:

**Excludes the following:**
- numpy (it was installed manually) 
- TensorFlow (we'll install 1.15.2 manually with pip)
- opencv-python (doesn't look like it's needed, it will be installed by conda as a dependency to one of the packages in requirements2.txt)

**Other changes:**
- sets scipy==1.4.1 to be compatible with TF 1.x) 
- installs jupyter

*Note: some packages may be installed from conda-forge, make sure to check if it is listed as a source*

    pip3 install tensorflow==1.15.2 (1.15.0 has a security issue and 1.15.2 has support for both cpu and gpu)
Clone the [Mask R-CNN repo](https://github.com/matterport/Mask_RCNN)

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
