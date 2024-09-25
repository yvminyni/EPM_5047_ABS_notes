# EPM_5047_ABS_notes
EPM 5047 Applied Bayesian Statistical Analysis Notes

  <!---[emoji-cheat-sheet ](https://github.com/ikatyang/emoji-cheat-sheet?tab=readme-ov-file#emoji-cheat-sheet)--->


:space_invader: YouTube playlist - [PyMC Examples](https://www.youtube.com/playlist?list=PLup8IWMcPX4pOyyDZp_Jn2rutSpIIJnmN).

:rocket: Installation instructions:
  [Install instruction 2024-0 連結](https://docs.google.com/document/d/1vAFaA7bBrA4V72iwXyycfAGqQPoxZWb6MxQkEj43A-o/edit?usp=sharing)

  <!---[Install_instruction_2024_html](https://github.com/yvminyni/EPM_5047_ABS_notes/blob/main/0820_Install_instruction-output_html.html) --->

:flying_saucer: Colab Examples:
  
  點擊 連結 後，於頁面左上角點選 `檔案>>在雲端硬碟中儲存副本`，即可在自己的Google Drive建立筆記本副本變更程式碼實際操作。

  - [PyMC Example 1 & 2](https://colab.research.google.com/drive/16ExYLitGks70uWHn8MOoL9JqsjZID6tZ?usp=sharing)
  <!---[PyMC_example.ipynb](https://colab.research.google.com/drive/1opFXvCPnOgRyTcNZE3arbTwRlcGoW5WI?usp=sharing) --->

  - ...

  - Executed on Google Colab: [Get started](https://colab.research.google.com/)
<!---
  (https://colab.research.google.com/drive/1Mhs_c9DBNYwtHE2cjfzd92YCnBSCgWP-?usp=sharing)
--->

<!---pymc_environment.yml:
![pymc_env_yml](https://github.com/yvminyni/EPM_5047_ABS_notes/blob/main/ABS_picture/create_environment_yml.jpg)
--->



## Environment
- Alternative environment file: [bap3.yml](https://github.com/yvminyni/EPM_5047_ABS_notes/blob/main/bap3.yml). 
[Source github](https://github.com/aloctavodia/BAP3/tree/main).
  
  <!---![bap3_env](https://github.com/yvminyni/EPM_5047_ABS_notes/blob/main/ABS_picture/bap3_env.png)--->
  <div align="center">
  <img src="https://github.com/yvminyni/EPM_5047_ABS_notes/blob/main/ABS_picture/bap3_env.png" width="300"  />
  </div>




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

    例如: ExecutableNotFound: failed to execute WindowsPath('dot'), make sure the Graphviz executables are on your systems' PATH
    
    (sol.1)先關閉jupyter notebook，打開anaconda prompt，在該環境(以pymc_env環境為例)下重載python-graphviz
    
```
conda activate pymc_env
conda install -c conda-forge python-graphviz
```
  (Solution.2) https://blog.finxter.com/graphviz-executables-not-found-error-fixed/

  (Solution.3) https://blog.csdn.net/qq_45956730/article/details/126689318

----
## Anaconda Environment Tips :wrench:

Update to the latest conda version.
```
conda update -n base -c defaults conda
```

Check existing environments. 

Check packages under this activated environment (my_env).
```
conda env list
conda activate my_env
conda list 
```

Check existing jupyter kernels. (Kernels you can find when you open jupyter notebook.)

Remove specific kernel (my_kernel).
```
jupyter kernelspec list
jupyter kernelspec remove my_kernel
```
Check existing environments. 

Remove specific conda environment (my_env).
```
conda env list
conda env remove --name my_env
```
Read the enviornment.yml file through location to create a new environment (myenv_name).

Install ipython kernel for this environment, so that users can find this environment while coding with jupyter notebook.
```
conda env create --file C:\Users\User\Desktop\environment.yml --name myenv_name
ipython kernel install --user --name = myenv_kernelname
```

Export the environment.

Export the environment without showing up on your local path. (Windows operating system).
```
conda env export > environment.yml

conda env export | grep -v "^prefix: " > environment.yml
```
The exported environment.yml file would be found at `C:\Users\user`.


### Reference:
1. [Removing Conda environment](https://stackoverflow.com/questions/49127834/removing-conda-environment)
2. [Anaconda｜在 Jupyter notebook 中建立、移除虛擬環境](https://medium.com/programming-with-data/%E5%9C%A8-jupyter-notebook-%E4%B8%AD%E5%BB%BA%E7%AB%8B-%E7%A7%BB%E9%99%A4%E8%99%9B%E6%93%AC%E7%92%B0%E5%A2%83-6c90c89791a5)
3. [How to Export Your Anaconda Environment: A Step-by-Step Guide](https://pythontwist.com/how-to-export-your-anaconda-environment-a-step-by-step-guide)
4. [Anaconda export Environment file](https://stackoverflow.com/questions/41274007/anaconda-export-environment-file)
