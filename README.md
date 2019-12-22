# vize

#include <stdio.h>
#include <string.h>
#include <stdlib.h>

void tabloyugoster(int a[][50],int b) ;
int *rasgele();
void tara(int big[][50], int b, int ras[], int rs);

int main() {
	srand(time(NULL));
	int i,j,big_arr[50][50];
	
	for(i=0;i<50;i++) {
		for(j=0;j<50;j++) {
			big_arr[i][j] = rand()%10;
		}
	}

	int *rptr;
	rptr=rasgele();

	tara(big_arr,50,rptr,25);
	
	return 0;
}

void tabloyugoster(int a[][50],int b) {
	int i,j;
	for(i=0;i<b;i++){
		for(j=0;j<b;j++){
			printf("%d ",a[i][j]);
		}
		puts("\n");
	}
}

int* rasgele() {
	
	static	int rasgelenler[25];
	int i;
	for(i=0;i<25;i++) {
		rasgelenler[i] = rand()%9000+1000;
	}
	
	
	return rasgelenler;
}

void tara(int big[][50], int b, int ras[], int rs) {
	
	int k,i,j;
	int fsay,nfsay;
	int found[50];
	int nfound[50];
	for(i=0;i<50;i++){
		found[i]=0;
		nfound[i]=0;
	}
	
	for(k=0;k<25;k++){
	for(i=0;i<b;i++){
		for(j=0;j<b;j++){
			if( (big[i][j]*1000+big[i][j+1]*100+big[i][j+2]*10+big[i][j+3] ) == ras[k] || (big[i][j]*1000+big[i-1][j]*100+big[i-2][j]*10+big[i-3][j] ) == ras[k] )  {
				found[k]=ras[k];
			}
			else {
				nfound[k]=ras[k];
			}
		}
	}
}


for(k=0;k<50;k++) {
	if(found[k]!=0){
		printf("Number that are found : %d\n", found[k] );
	}
}

for(k=0;k<50;k++) {
	if(nfound[k]!=0){
		printf("Number that are not found : %d\n", nfound[k] );
	}
}

	
} 









