# CSE597-Final-Project
Final Project for CSE597

This is a recreation of https://github.com/Hao840/ADEM-VL ADEM-VL code.

These instructions mostly follow the readme listed there.

1. Download the ScienceQA dataset from here [https://github.com/lupantech/ScienceQA](url).

2. Download the LLaMA 7B model, this can be found on the ADEM-VL github. This is very large so you may have to copy it in to colab from your drive like I did.

3. Organize your file structure as shown in the ADEM-VL github. The notebook should structure the important things for you and unzip the data if necessary

   ![image](https://github.com/user-attachments/assets/5d588db8-4687-47ce-904f-131cfff57d46)

   Some notes: Make sure params.json is both in weights and the sub folder for the model. Also tokenizer.model is not a subfolder but a file, 7B and 13B are not subfolders of it. 

5. Add this line to train.py line 24: parser.add_argument('--llama_model_path', type=str, default=None) . This fixes an error where the arguments won't properly pass to build.py

6. In eval_sqa.py change line 159: adapter = torch.load(os.path.join(args.adapter_path, 'checkpoint-19.pth'))['model']. Where checkpoint-19.pth, insert the name of your model whether its the one you trained or their pretrained weights (can also be found on their github).

7. After this you should be able to run the functions as written in the notebook and adjust hyperparameters as necessary.

