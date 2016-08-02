vigenere

kmee

kmeee

    int main(int argc, string argv[])
    {
    //samo jedan argument!
    if( argc != 2 )
    {
    printf("error\n");
    return 1;
    }
    
    //zatraži ulazni tekst
    string s = GetString();
    string k = argv[1];
    
        //prva for-petlja:iterira kroz tekst
        for(int i = 0, m = strlen(s); i < m; i++)
        {   
            int kj;
            //druga for-petlja: iterira kroz ključ
            for(int j = 0, n = strlen(k); j < n; j++)
            {
            int d = (int)k[j];
        
            if(d >= 97 && d <= 122)
            kj = d - 'a';
            
            else if(d >= 65 && d <= 90)
            kj = d - 'A';
            //alphabetical only
             else
            {
            printf("error\n");
            return 1;
            }
            //if-then, do-while??
            }
        
        int c = (int)s[i];
        
        if(c >= 97 && c <= 122)
        printf("%c", (c - 'a' + kj) % 26 + 'a');
        
        else if(c >= 65 && c <= 90)
        printf("%c", (c - 'A' + kj) % 26 + 'A');
        
        else
        printf("%c", c);
    
        }
        printf("\n");
    }
