# OCR-TO-TRANSLATION DEMO
A fast solution for recognising text from images from various languages using Tesseract and translating the recognised text to english exploiting the pre-trained models from Transformers in Python 3.7.


## **OCR-TRANSLATION USE CASE**

#### STEPS

1.The first step is to install Tesseract. 
* For Windows users the executable file can be downloaded from this [list](https://digi.bib.uni-mannheim.de/tesseract/). Whereas for the needs of this project we used Tesseract 4 version which can be downloaded by clicking [here](https://digi.bib.uni-mannheim.de/tesseract/tesseract-ocr-w64-setup-v4.1.0.20190314.exe). For more information about the installation of Tesseract on Windows please read this article in [medium](https://medium.com/quantrium-tech/installing-and-using-tesseract-4-on-windows-10-4f7930313f82).

* For macOs using Homebrew can be used to install Tesseract. 
 
     `$ brew install tesseract`
     
* For Ubuntu users apt-get can be used to install Tesseract. 
 
     `$ sudo apy-get install tesseract-ocr`
     
* For Centos7 systems you can find the instructions [here](https://github.com/second-state/OCR-tesseract-on-Centos7).

- For more information about Tesseract have a look on these: [pytesseract github](https://github.com/madmaze/pytesseract), [ocr tutorial](https://nanonets.com/blog/ocr-with-tesseract/) 

2.The next step is to install the language packages for the languages we wish Tesseract to recognise from the images and find the abbreviations of the language to introduce them to the scripts.

* **Windows :** Since we have built the demo on a Windows machine the next step is to download the language packages and store them in the Tessdata folder which can be found in the Tesseract folder (e.g. C:\Program Files\Tesseract-OCR\tessdata). The list of the available languages that Tesseract can recognise can be found [here](https://github.com/tesseract-ocr/tessdata/)
 
*  **Other OS**: For installing the language packages on other operation systems you can find the instructions [here](https://ocrmypdf.readthedocs.io/en/latest/languages.html).

3.Create a new python virtual environment.

* Python

     `pip install virtualenv`

     `python -m virtualenv your_environment_name` or `python -m virtualenv your_environment_name -p=<C:/path/to/python/version3.7/python.exe>`
     
     `your_environment_name\Scripts\activate`

* Conda 

    `conda create --name your_environment_name python=3.7`
    
    `conda activate your_environment_name`
    
    `pip install -r requirements.txt`
    
4.Install the libraries from the requirements.txt file.

   `pip install -r requirements.txt`
    
5.Now it's time to jump to the jupyter notebook. In the Jupyter notebook before we run the scripts we have to specify 
the local directory of the tesseract .exe file and the tessdata folder where the language packages should be downloaded stored. Alternatively, you can set these paths as environment variables.

    pytesseract.pytesseract.tesseract_cmd = "C:/Program Files/Tesseract-OCR/tesseract.exe"
    tessdata_dir_config = '--tessdata-dir "C:/Program Files/Tesseract-OCR/tessdata"'
    
6.You are ready to go and run the script! First, define the directory of the folder where the images exist. Then, make sure that you are 
connected to internet to run the method `image_to_ocr_translation_online`, because in this step the script downloads from the internet and stores the pre-trained 
language packages needed for translating the text (i.e.MarianMTModel method/algorithm). The pre-trained language packages are stored in the same directory 
where the images are. Now, you can disconnect from the internet and run the `image_to_ocr_translation_offline` method for performing the same functionality. 
 
 
*Bear in mind for more languages first you have to download the tesseract language models for the ocr function and for the translation you have to find the name of the corresponding language model (e.g. model_name) to call it in the MarianMTModel function.



      
