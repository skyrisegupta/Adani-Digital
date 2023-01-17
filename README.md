# Adani-Digital
Answer of Adani Digital Lab


#include <bits/stdc++.h>
using namespace std;
  
int rows,col,col_sort;
 
bool sort_col(const vector<int>& v1, const vector<int>& v2)
{   
	return v1[col_sort-1] < v2[col_sort-1];
}

  //Part -1 Generating an array with no between 1 to 100
					       
  vector<vector<int>> ARRAY_GENERATOR( int rows ,int col ) 
  {
       vector<vector<int>> ARR(rows,vector<int>(col,0));

    for (int i=0; i<rows; i++)
        for (int j=0; j<col; j++)
                ARR[i][j] = (rand() % 100); 

    cout << "Random generated 2D-Array :" << endl;

    for (int i=0; i<rows; i++){
        for (int j=0; j<col; j++)
            cout << ARR[i][j] << " ";
        cout << endl;
    }
    return ARR;
  }
  
  
   //Part 2 - Sorting a particular column
	
  vector<vector<int>> ARRAY_SORTER( vector<vector<int>> ARR, int col_sort)
   {
       
       sort(ARR.begin(), ARR.end(), sort_col);
	cout << "The 2D Array after sorting is:\n";
	for (int i = 0; i < rows; i++) {
		for (int j = 0; j <col; j++)
			cout << ARR[i][j] << " ";
		cout << endl;
	}
       
      return ARR; 
   }
int main()
{
    //Input
    // rows for no of rows in 2-D Array
    // col for no of columns in 2-D Array
    // col_sort is the column no to be sorted 
    
    cout<<"Enter number of rows=";
    cin>>rows;

    cout<<"Enter number of columns=";
    cin>>col;
   
    while(1)
    {
        cout<<"Enter the column to be sorted=";
        cin>>col_sort;
        
        if(col_sort>col)
             cout<<"Please Enter a valid column ranging from 1 to "<<col <<endl;
         else
             break;
    }
    
    
    
    vector<vector<int>> ARR;
    ARR=ARRAY_GENERATOR(rows,col);


    ARR=ARRAY_SORTER(ARR,col_sort);
	
	return 0;
}
