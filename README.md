# english_accent_classifier

В этом репозитории находится реализация работы по созданию модели для классификации акцентов английского языка, инструкция по её эксплуатации, исходный датасет.

Также здесь содержится ссылка на готовую модель и приведена инструкция по тому, как с её помощью можно классифицировать акцент дял внешних датасетов.

1) Тренировка модели

Для повторения или изменения процедуры тренировки необходимо установить среду jupyter-notebook, загрузить исходный датасет по ссылке :
https://drive.google.com/drive/folders/16yvBUWeUKDBIymsYeQIA2H8YEQFfpoyR?usp=sharing
Проверить, чтобы он находился в репозитории /audio относительно исполняемого файла. Затем следовать инструкции в блокноте classifier.ipynb для тренировки модели и возможного улучшения, например настройки гиперпараметров или изменения архитектуры.

Не обязательно скачивать весь датасет. Готовые финальные виды данных для тренировки загружены и находятся в репозитории https://huggingface.co/TheHolyPacman под названиями train_dataset, eval_dataset, test_dataset. Из можно загрузить использую функцию load_dataset из библиотеки transformers. 

2) Использование модели
   
Готовые веса модели могут быть загружены с репозитория :
   https://drive.google.com/drive/folders/1KJCrLk_sZPZiMgJMQmdwT8cdWsl7x2oC?usp=sharing
После чего анализируемый датасет необходимо привести к образцу : https://huggingface.co/datasets/TheHolyPacman/train_dataset_2
Далее следует использовать функцию преобработки wav2vec2 для корректных входных данных на модель (пример правильного результата после : https://huggingface.co/datasets/TheHolyPacman/test_dataset_2_mod)
С данными в таком виде можно выполнять функции классификации типа акцента по примеру работы исходной модели.

Образец того, как данные можно привести к необходимому виду приведены в файле external_data.ipynb на примере датасета common voice.

Список библиотек, используемых в задании, полученных через функцию version (для корректной работы программы):

from importlib.metadata import version

version('numpy') 	'1.26.2'
version('pandas')	'2.1.3'
version('torchaudio')	'2.1.1'
version('librosa')	'0.10.1'
version('IPython')	'7.31.1'
version('transformers')	'4.36.0.dev0'
version('torch')		'2.1.1'
version('accelerate')	'0.25.0'
version('wandb')	'0.16.0'
version('matplotlib')	'3.5.1'
version('tqdm')		‘4.66.1'
version('datasets')	'2.15.1.dev0'
version('jiwer')		'3.0.3'
version('typing')	'3.7.4.3'

from sklearn import __version__
print(__version__)  1.3.2


Команды, необходимые для их установки :

pip install 'numpy==1.26.2' --force-reinstall
pip install 'pandas==2.1.3' --force-reinstall
pip install 'torchaudio==2.1.1' --force-reinstall
pip install 'librosa==0.10.1' --force-reinstall
pip install 'IPython==7.31.1' --force-reinstall
pip install 'transformers==4.36.0' --force-reinstall
pip install 'torch==2.1.1' --force-reinstall
pip install 'accelerate==0.25.0' --force-reinstall
pip install 'wandb==0.16.0' --force-reinstall
pip install 'matplotlib==3.5.1' --force-reinstall
pip install 'tqdm==4.66.1' --force-reinstall
pip install 'datasets==2.15.0' --force-reinstall
pip install 'jiwer==3.0.3' --force-reinstall
pip install 'typing==3.7.4.3' --force-reinstall
