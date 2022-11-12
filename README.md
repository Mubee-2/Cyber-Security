[Mubarak Aliyu Danjuma Report 2 updated.pdf](https://github.com/Mubee-2/Cyber-Security/files/9946558/Mubarak.Aliyu.Danjuma.Report.2.updated.pdf)
[Mubarak Aliyu Danjuma Report 5.pdf](https://github.com/Mubee-2/Cyber-Security/files/9946562/Mubarak.Aliyu.Danjuma.Report.5.pdf)
# web exploitation#Cryptography

We found this weird message being passed around on the servers, we think we have a working decryption scheme.
Download the message https://artifacts.picoctf.net/c/395/message.txt
Take each number mod 37 and map it to the following character set: 0-25 is the alphabet (uppercase), 26-35 are the decimal digits, and 36 is an underscore.
Wrap your decrypted message in the picoCTF flag format (i.e. picoCTF{decrypted_message})

import string
List = [202,137,390,235,114,369,198,110,350,396,390,383,225,258,38,291,75,324,401,142,288,397]
for items in List:
    if items%37 in range(0, 26):
        print(string.ascii_uppercase[items%37], end="")
    elif items%37 in range(26, 36):
        print(string.digits[items%37-26], end="")
    else:
        print('_', end="")
