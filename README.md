# audio_cv
here my cv is uploded to read.


import PyPDF3
import pyttsx3
engine= pyttsx3.init()
engine.setProperty('rate',150) #to set the speaking rate
path=r"C:\Users\HP\OneDrive\Desktop\shagufa parveen___.pdf"
cv=open(path,'rb')      #open the file to read in binary mode
cvReader= PyPDF3.PdfFileReader(cv)
no_of_pages=cvReader.numPages #counts the total num of pages
repeat=1
while repeat==1:
    for i in range (no_of_pages):
        page=cvReader.getPage(i)
        text=page.extractText()
        engine.say( text)
        engine.runAndWait()

    engine.say("thanks for listening, if you want to listen again please press 1 otherwise press 2 ")
    engine.runAndWait()
    repeat=int(input("enter here - "))
    
        
