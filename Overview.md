# MNIST
followed this tutorial https://www.youtube.com/watch?v=bte8Er0QhDg

https://www.tensorflow.org/install/pip#windows-wsl2_1
1) checked python version via command prompt "python --version" -> Python 3.8.8
2) checked pip version via command prompt "pip --version" ->pip 21.3 and filepath
3) checked numpy installation via command prompt "python -m pip show numpy"
4) installed opencv using this guide: https://docs.opencv.org/4.x/d5/de5/tutorial_py_setup_in_windows.html
5) verified opencv installation via python prompt in spyder
>>> import cv2 as cv
>>> print( cv.__version__ )
6) verified matplotlib installation via python prompt in spyder
>>> import matplotlib
>>> matplotlib.__version__
7) verified graphics card has cuda architecture
Settings > System Information > Hardware Resources > Memory
https://developer.nvidia.com/cuda-gpus
8) verfied tensorflow requriements
-> graphics card is good
-> Python 3.8-3.11 (good)
-> pip 19.0 or higher
9) installed CUDA toolkit
https://developer.nvidia.com/cuda-toolkit-archive  
10) downloaded tensorflow following this tutorial https://www.tensorflow.org/install/pip#windows-wsl2_1 
- I had to restart my computer after installing WSL2
- I had this error https://discuss.tensorflow.org/t/tensorflow-installation-error/15889/10 and was not able to setup GPU

when I tried running this in spyder it did not work.
I tried this process of setting up spyder in a different environment https://medium.com/@pushkarmandot/installing-tensorflow-theano-and-keras-in-spyder-84de7eb0f0df

tried this next but was not able to get it working
https://github.com/wxs/keras-mnist-tutorial/blob/master/MNIST%20in%20Keras.ipynb
instead of source keraenv/bin/activate I used C:\Users\johnw>C:\Users\johnw\kerasenv\scripts\activate.bat

then retried the original method, using a video to follow along. this ended up working! It helped me realize I was not in the right virtual environment on the first attempt.
https://www.youtube.com/watch?v=0S81koZpwPA

I then followed this to get jupyter notebook running in the virtual environment
https://towardsdatascience.com/configuring-jupyter-notebook-in-windows-subsystem-linux-wsl2-c757893e9d69
these helped with errors
https://stackoverflow.com/questions/10572498/importerror-no-module-named-sqlalchemy
https://blog.finxter.com/fixed-modulenotfounderror-no-module-named-chardet/

I then followed this tutorial
https://youtu.be/eU0FFjYumCI

I could not get it to run without throwing a dst-tensor-is-not-initialized" error. the workaround was to use cpu only :(
Some day I'll figure out GPU support
the way I did this was to tell tensorflow there arent any gpus: tf.config.set_visible_devices([], 'GPU')