# commonChild-Java
For Example ,let s1="abcdaf",s2="acbcf";
//arr[0][0->s1.length]=0
//arr[0->s2.length][0]=0
for(int i=1;i<=s1.length();i++)
{
    for(int j=1;j<=s2.length();j++)
    {
    //here we are checking whether the character at "i" in s2 equals to character at "j" in s1.
    //If so we will add 1 to arr[i-1][j-1] and assign it to arr[i][j] as the maximum commom length till this character will be at arr[i-1][j-1].
        if(s2.charAt(i-1)==s1.charAt(j-1))
        {
            arr[i][j]=arr[i-1][j-1]+1;
        }
        //here if the character at "i" in s2 not equal to character at "j" in s1 then we will be taking max value of (arr[i-1][j],arr[i][j-1]).  
        else
        {
            arr[i][j]=Math.max(arr[i-1][j],arr[i][j-1]);
        }
    }
}
the longest common subsequence length will be at arr[s1.length()][s2.length()];
