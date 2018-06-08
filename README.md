# Passwords
Secure Passwords

Code

 #generates a random 32-bit AES key 


$KeyFile = "D:\directory\KeyFile\AES.key" 


$Key = New-Object Byte[] 32 


[Security.Cryptography.RNGCryptoServiceProvider]::Create().GetBytes($Key) 


$Key | out-file $KeyFile 



#create the encryped password using the key above


$PasswordFile = "D:\directory\KeyFile\AESPassword.txt" 


$KeyFile = "D:\directory\KeyFile\AES.key"


$Key = Get-Content $KeyFile


#change the value of $password to your password before running! 


$Password = "Password" | ConvertTo-SecureString -AsPlainText -Force 


$Password | ConvertFrom-SecureString -key $Key | Out-File $PasswordFile  
