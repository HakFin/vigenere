vigenere

kmee

kmeee

    /*
Vigenereova šifra: https://www.youtube.com/watch?v=9zASwVoshiM
*/

#include <stdio.h>
#include <cs50.h>
#include <string.h>
#include <ctype.h>
#include <stdlib.h>

int kljuc(int slovoteksta, char c, string k);

int main(int argc, string argv[])
{
    //samo jedan argument!
    if( argc != 2 )
    {
    printf("error\n");
    return 1;
    }
    
    string k = argv[1];
    
    //argument mora biti slovo abecede!
    for(int i = 0, n = strlen(k); i < n; i++)
    {
        if(!isalpha(k[i]))
        {
        printf("error\n");
        return 1;
        }
    }
    
    //zatraži ulazni tekst
    string s = GetString();
    
    int slovoteksta = 0;
    
    for(int i = 0, m = strlen(s); i < m; i++)
    {
        char c = s[i]; 
        
        if(islower(c))
        {
        printf("%c", (c - 'a' + kljuc(slovoteksta,c,k)) % 26 + 'a');
        slovoteksta++;
        }
        
        else if(isupper(c))
        {
        printf("%c", (c - 'A' + kljuc(slovoteksta,c,k)) % 26 + 'A');
        slovoteksta++;
        }
        
        else
        printf("%c", c);
     }
    printf("\n");
}

//ključ!
int kljuc(int slovoteksta, char c, string k)
{
    int kj;
    int n = strlen(k);
    int slovoključa = k[slovoteksta % n];
                
    if(islower(slovoključa))
    {
    kj = slovoključa - 'a';
    }
    
    else(isupper(slovoključa));
    {
    kj = slovoključa - 'A';
    }
    
    return kj;
}
