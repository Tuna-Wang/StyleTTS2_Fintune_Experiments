## HOW TO USE THE FINETUNED VERSION
The original StyleTTS2 provided jupyter notebooks for fine-tuning, the file is located in the Colab folder. <font color="red">For the purpose to avoid timbre feature cloning, we made modifications to the train_finetune.py and models.py, make sure you replace the two files with the files in this branch.</font> However, you should make small modifications to add in your own training data.  

### Suggestions on datasets
1. The audio data should be saved in a folder named 'wavs' under Data directory.  
2. Prepare 3 txt  files: training_list.txt, val_list.txt, OOD_texts.txt. Refer to the original files provided by StyleTTS2 for content. The training_list.txt, val_list.txt should contain:

audio.wav | IPA transcription | Speaker ID |
| :------- | :------: | -------: |
| name of audio  | Phonetic symbols transcription of the text | 0  |

For the OOD_texts.txt, the name of the audio is not important(you can put some dummy audio names, they don't need to be real); the IPA transcription is enssential; set the Speaker ID to something like 99999 so it does not conflict with your Speaker IDs in the training or testing dataset.  
3. The original fine-tune demo uses LJSpeech. It is better to align your training data to the standard of LJSpeech (single-channel 16-bit PCM WAV with a sample rate of 22050 Hz)

### Other Suggestions
1. You can go to the Configs folder to change the congfigurations in config_ft.yml.  
2. Use cuda to avoid troubles.

