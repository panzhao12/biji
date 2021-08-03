
#### 1. 二维数组优化
```Java
public static double[][] mult(double[][] A, double[][] B, int size) {
	    double[][] C = new double[size][size];  
	    for (int i = 0; i < size; i++) {  
		    for (int j = 0; j < size; j++) {   //--这两行对调
		        for (int k = 0; k < size; k++) {  //--这两行对调
		            C[i][j] += A[i][k] * B[k][j];  
				}  
		     }  
		}  
		return C;  
	}
```
因为memory layout of the data structure，将j和k对调（先逐个算行后算列）。
