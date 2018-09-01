# Hiden Agenda

### Difficulty : Medium

## Description
Just before getting caught in Russia, MI-6 agent John Stegwal sent a mail to MI-6 containing two visually similar images. It is possible that the images contain information on how to access his findings. Can you find the message he sent?

## Hint
- Look for algorithms for steganography in jpeg images and use the available implementation.

## Walk-through
- We initially get two images which look very similar although one is 4MB in size and the other is around 10MB
- The most obvious approach on getting two images is to take their diff and then see what is hidden there.
- Opening in GIMP and taking the difference of two layers(having the images) we get a completely black image. Showing no difference.
![gimp](https://github.com/cb1711/CodefestCTF_2018/blob/master/Screenshot%20from%202018-09-02%2000-44-30.png)

- On flattening the image and tweaking the brightness and contrast we get a QR code.
![QRcode](https://github.com/cb1711/CodefestCTF_2018/blob/master/Screenshot%20from%202018-09-02%2000-57-12.png)

- Scanning the QR code leads us to an image having a troll  face. Though flag{ is written in the image but the flag is not there.(Its just a decoy).
![Troll](https://github.com/cb1711/CodefestCTF_2018/blob/master/Screenshot%20from%202018-09-02%2001-15-02.png)
- One can look for the techniques for steganography in jpeg images. After going through some of them one can get to [JSteg](https://www.youtube.com/watch?v=TWEXCYQKyDc) (Link on how Jsteg works).
- On looking for implementations for JSteg one can find [Jstego](https://sourceforge.net/projects/jstego/)
- Running the jar file, selecting Seek option and then selecting the first image shows that there is another file hidden by the name flg.exe which has been extracted by the program
![Jstego](https://github.com/cb1711/CodefestCTF_2018/blob/master/Screenshot%20from%202018-09-02%2001-19-58.png)
- Using *file flg.exe* shows that the file is an mp3 file. So the flag is hidden in the mp3 file.
![File](https://github.com/cb1711/CodefestCTF_2018/blob/master/Screenshot%20from%202018-09-02%2001-21-30.png)
- To get the flag from audio open it in Audacity or any other software which can analyze audio
![Audacity](https://github.com/cb1711/CodefestCTF_2018/blob/master/Screenshot%20from%202018-09-02%2001-36-10.png)
- Generate a spectrogram of the image and the flag will be visible.
![Flag](https://github.com/cb1711/CodefestCTF_2018/blob/master/Screenshot%20from%202018-09-02%2001-22-32.png)

## Flag
CodefestCTF{0b5cUr17y > 53cur17y}


