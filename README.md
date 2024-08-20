# EPM_5047_ABS_notes
EPM 5047 Applied Bayesian Statistical Analysis Notes

pymc_environment.yml:

![pymc_env_yml](https://github.com/yvminyni/EPM_5047_ABS_notes/blob/main/ABS_picture/create_environment_yml.jpg)

- Alternative environment file: [**bap3.yml**](https://github.com/yvminyni/EPM_5047_ABS_notes/blob/main/bap3.yml)
  
  [Source](https://github.com/aloctavodia/BAP3/tree/main)

- Installation instructions:
    
  [Install_instruction_2024.ipynb待補連結]

  [Install_instruction_2024_html](https://github.com/yvminyni/EPM_5047_ABS_notes/blob/main/0820_Install_instruction-output_html.html)

- Examples:

  點擊[連結](https://colab.research.google.com/drive/1opFXvCPnOgRyTcNZE3arbTwRlcGoW5WI?usp=sharing)後，於頁面左上角點選 `檔案>儲存>>在雲端硬碟中儲存副本`，即可在自己的Google Drive建立筆記本副本變更程式碼實際操作。

- Executed on Google Colab:

   [Read your data and get started](https://colab.research.google.com/drive/1Mhs_c9DBNYwtHE2cjfzd92YCnBSCgWP-?usp=sharing)


----
## Debugging:

0. 如果在Install_instruction 的 step 2 就在安裝上產生問題，可以改成讀取bap3.yml檔案來建立環境:

    C:\Users\user\Desktop\bap3.yml 需自行修改檔案位置
```
conda env create --file C:\Users\user\Desktop\bap3.yml --name pymc_env
```

1. 如果 jupyter notebook 沒出現environment的kernel:
   
   (以pymc_env環境為例) 先關閉jupyter notebook，再次打開anaconda prompt，更新ipykernel並重新安裝kernel，輸入:
```
conda activate pymc_env
conda install -y ipykernel
python -m ipykernel install --user --name=pymc_env
```

2.  如果執行程式時，出現和graphviz、python-graphiz相關的error或path error:

    先關閉jupyter notebook，打開anaconda prompt，在該環境(以pymc_env環境為例)下重載python-graphviz
```
conda activate pymc_env
conda install -c conda-forge python-graphviz
```
