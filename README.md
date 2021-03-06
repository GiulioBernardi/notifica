I made this script to automate a manual process to check if a table was updated by another team.

Everyday, me and my team open the company directories, we open folder after folder to find the excel file, and then we need to check the last modified date to see if it was update recently.

I googled some way to solve this problem and I found [this tutorial](https://tonyteaches.tech/detect-file-change-python/) teaching how to check for update in pdf's

So I used it as inspiration to think in my own logic.

![Flow Diagram](https://github.com/GiulioBernardi/fotos/blob/master/Notifica_method.drawio.png)

The diagram itself was made in portuguese, but it explains the following order of processing:

1. First of all, the script go to the my company's directory that the excel files is stored and then copy to a local file;
2. By using <pre><code>shutil.copy2</code></pre> function from [shutil lib](https://docs.python.org/3/library/shutil.html#shutil.copy2), the script's able to use the metadata of the copied files;
3. Store the last modified date of both files in variables;
4. Compare the variables;
5. If there is an update, an e-mail will be send.

Let's suppose that I need to watch the File1 to update the File2(When File1 got an update, I'll need to update File2). Instead of going manualy to the directory and checking the last modified date, the scrip does it for me. It checks if the last modified date of File1 is greater then the last modified date of File2, and if it is, an e-mail will be send to me, telling that I need to check for updates in File1.
