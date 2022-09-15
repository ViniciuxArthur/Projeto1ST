import threading
import numpy as np
import time

A = np.random.randint(10, size=(4, 4))	

B = np.random.randint(10, size=(4, 4))	

R = [[0,0,0,0],[0,0,0,0],[0,0,0,0],[0,0,0,0]]



def multiplicandomatrizes(A,B):
    
    
    RP = [A[0][0] * B[0][0],A[0][1] * B[0][1],A[0][2] * B[0][2], A[0][3] * B[0][3],
        A[1][0] * B[1][0], A[1][1] * B[1][1], A[1][2] * B[1][2], A[1][3] * B[1][3],
        A[2][0] * B[2][0], A[2][1] * B[2][1], A[2][2] * B[2][2], A[2][3] * B[2][3],
        A[3][0] * B[3][0], A[3][1] * B[3][1], A[3][2] * B[3][2], A[3][3] * B[3][3]]
    
    print()
    print("Produto da multiplicação posicional: ")    
    print (RP[0]," ",RP[1]," ",RP[2]," ",RP[3])
    print (RP[4]," ",RP[5]," ",RP[6]," ",RP[7])
    print (RP[8]," ",RP[9]," ",RP[10]," ",RP[11])
    print (RP[12]," ",RP[13]," ",RP[14]," ",RP[15])  



    RM = [[A[0][0] * B[0][0] + A[0][1] * B[1][0] + A[0][2] * B[2][0] + A[0][3] * B[3][0],
    A[0][0] * B[0][1] + A[0][1] * B[1][1] + A[0][2] * B[2][1] + A[0][3] * B[3][1],
    A[0][0] * B[0][2] + A[0][1] * B[1][2] + A[0][2] * B[2][2] + A[0][3] * B[3][2],
    A[0][0] * B[0][3] + A[0][1] * B[1][3] + A[0][2] * B[2][3] + A[0][3] * B[3][3]],
    [A[1][0] * B[0][0] + A[1][1] * B[1][0] + A[1][2] * B[2][0] + A[1][3] * B[3][0],
    A[1][0] * B[0][1] + A[1][1] * B[1][1] + A[1][2] * B[2][1] + A[1][3] * B[3][1],
    A[1][0] * B[0][2] + A[1][1] * B[1][2] + A[1][2] * B[2][2] + A[1][3] * B[3][2],
    A[1][0] * B[0][3] + A[1][1] * B[1][3] + A[1][2] * B[2][3] + A[1][3] * B[3][3]],
    [A[2][0] * B[0][0] + A[2][1] * B[1][0] + A[2][2] * B[2][0] + A[2][3] * B[3][0],
    A[2][0] * B[0][1] + A[2][1] * B[1][1] + A[2][2] * B[2][1] + A[2][3] * B[3][1],
    A[2][0] * B[0][2] + A[2][1] * B[1][2] + A[2][2] * B[2][2] + A[2][3] * B[3][2],
    A[2][0] * B[0][3] + A[2][1] * B[1][3] + A[2][2] * B[2][3] + A[2][3] * B[3][3]],
    [A[3][0] * B[0][0] + A[3][1] * B[1][0] + A[3][2] * B[2][0] + A[3][3] * B[3][0],
    A[3][0] * B[0][1] + A[3][1] * B[1][1] + A[3][2] * B[2][1] + A[3][3] * B[3][1],
    A[3][0] * B[0][2] + A[3][1] * B[1][2] + A[3][2] * B[2][2] + A[3][3] * B[3][2],
    A[3][0] * B[0][3] + A[3][1] * B[1][3] + A[3][2] * B[2][3] + A[3][3] * B[3][3]]]

    print()
    print("Produto da multiplicação matricial: ")
    print(RM[0])
    print(RM[1])
    print(RM[2])
    print(RM[3])

if __name__ == "__main__":

    tempoinicial = time.perf_counter()
    print ()
    print ("Matriz A: ")
    print ()
    print (A)
    print ()
    print ("Matriz B: ")
    print ()
    print (B)
    print ()

    th1 = threading.Thread(target=multiplicandomatrizes,args=(A,B))

    th1.start()

    th1.join()

    tempofinal = time.perf_counter()

    print("Tempo de execução do programa: ",tempofinal-tempoinicial)
