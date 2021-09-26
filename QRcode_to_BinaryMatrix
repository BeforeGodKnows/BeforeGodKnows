from PIL import Image
import numpy as np   #numpy只能算方阵
import scipy as SP   #scipy可算非方阵
from scipy import linalg
import random 

def treatment(ima):
    ima=ima.convert('L')         #转化为灰度图像
    #ima.imshow()
    im=np.array(ima)        #转化为二维数组
    for i in range(im.shape[0]):#转化为二值矩阵
        for j in range(im.shape[1]):
            if im[i,j]==255:
                im[i,j]=0
            else:
                im[i,j]=1
    l0=len(im)
    l1=l0*l0
    print(l1)
    #l2=np.random.randint(1,l1)
    #print(l2)
    np.random.seed(1)
    A= np.array(random.randint(0,2,size = [2,l1]))
    #print(A)
    b = np.array([[1], [0]])
    #input()
    #求解矩阵Mi'
    pi_a = SP.linalg.pinv(A)
    s0 = pi_a.dot(b)
    s=np.array(s0)
    #x = np.linalg.solve(A, b)
    print(s)
    #for i in im:
    #    print(i)
    #    result2txt=str(i)          #前面运行出的数据，先将其转为字符串才能写入
    #   with open('test.txt','a') as file_handle:   # .txt可以不自己新建,代码会自动新建
    #        file_handle.write(result2txt)     # 写入
    #        file_handle.write('\n')         # 有时放在循环里面需要自动转行，不然会覆盖上一条数据
    input()
    for i in range(s.shape[0]):#转化为图片
        for j in range(s.shape[1]):
            if s[i,j]==0:
                s[i,j]=255
            else:
                s[i,j]=0
    new_im=Image.fromarray(s)
    new_im.show()

    
ima=Image.open('test.png') #读入图像
im=treatment(ima)  #调用图像处理函数
