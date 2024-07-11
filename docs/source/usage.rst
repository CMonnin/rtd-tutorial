Usage
=====

.. _installation:

Serving locally
------------

To use PictureNameingTask locally a simple http server can be used. Either download the dist from the github or build the package from source eg `npm build`. Then the index.html file can be served locally.
Python3 offers a command to serve the index.html locally with one command. First ensure python3 is installed. `It can be found here <https://www.python.org/downloads/>`. Choose the appropriate package for the OS that you have. 
Using a terminal or powershell first navitage to the directory containing the index.html file then:

.. code-block:: console

  cd path/to/directory/containing/index.html
  python3 -m http.server``

This will provide an ouput that looks something like this: 

.. code-block:: console

  Serving HTTP on 0.0.0.0 port 8000 (http://0.0.0.0:8000/) ...

To access this go to the provided url in your browser.
For example http://0.0.0.0:8000/
If port 8000 is already in use an error will be displayed.
To start the server on another port use (example 8080):

.. code-block:: console

   python -m http.server 8080

More information about `python http server` can be found here https://docs.python.org/3/library/http.server.html

Adding stimuli
----------------

Stimuli are added to the data.csv found in the `dist/assets` directory as follows:

.. csv-table:: stimuli :rst:dir:`csv-table`
   :header: "stimulus", "difficultyLevel", "correctResponse","language"

   "path/to/img_of_a_dog.jpg",    "1",      "A dog",          "EN"
   "path/to/img_of_a_cat.jpg",    "2",      "A cat",          "EN"
   "path/to/img_of_a_dog.jpg",    "1",      "Un chien",       "FR"
   "path/to/img_of_a_cat.jpg",    "2",      "Un chat",        "FR"

Changing experiment settings
----------------

Experiment settings are changed in the experimentSettings.csv file which can found in the `dist/assets` directory. These settings are described below:

- totalNumberOfTrialsToRun: this is the number of images to be shown, a number
- advancementSchedule: the number of correct answers that are required to increase the difficutly level by one, a number
- regressionSchedule: the number of incorrect answers required to decrease the difficutly level by one, a number
- language: the language of experiment, `EN` or `FR`
- seed: a seed for the psuedorandom number generator, a number 

.. csv-table:: experimentSettings :rst:dir:`csv-table`
   :header: totalNumberOfTrialsToRun, advancementSchedule, regressionSchedule, language, seed
   5, 2, 0, EN, 42


