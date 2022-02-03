I made this script to automate a manual process to check if a table was updated by another team.

Everyday, me and my team open the company directories. We need to open folder after folder to find the excel file, and then we need to check the last modified date before.

I googled some way to solve this problem and I found [this tutorial](https://tonyteaches.tech/detect-file-change-python/) teaching how to check for update in pdf's

So I used it as inspiration to think in my own logic.

![Flow Diagram](https://github.com/GiulioBernardi/fotos/blob/master/Notifica_metodo1.drawio.png)

The diagram itself was made in portuguese, but it explains the following order of processing:

1. First of all, the script go to the directory that the excel files is stored and then copy to a local file;
2. By using <pre><code>copy2</code></pre> function from <pre><code>shutil</code></pre> lib, LeI'm able to use the metadata of the copied files;
3. Store the last modified date of both files;
4. Compare de dates;
5. If there is an update, an e-mail will be send.

Let's suppose that I need to watch the File1 to update the File2. Instead of going manualy to the directory and checking the last modified date, the scrip does it for me. It checks if the last modified date of File1 is greater then the last modified date of File2, an e-mail will be send to me, telling that I need to check for updates in File1

