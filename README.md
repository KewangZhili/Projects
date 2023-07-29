**Papyrus Nebulae-Proj-1:**

**This project was done in GOOGLE COLABORAORY**
**------------------------------------------------------------------------------------------------------------------------------------**

                            **THIS PROJECT WAS A PART OF A HACKATHON CONDUCTED BY ADOBE INC.**

**------------------------------------------------------------------------------------------------------------------------------------**

**1.In this we were supposed to use ADOBE PDF Extract API and Python and were given 100 test invoices from which we had to extract out the required information as specified,and tabulate all the information collected from these 100 invoices**

**2.ADOBE PDF EXTRACT API::This is an API natively developed by ADOBE,It uses ML and to intelligently identify the bounding boxes,titles ,tables(if any) and images(if any) and extracts out all these contents in a json file and returns a zip folder containing all the above**

**3.My role started from here,I had to extract the contents of the file in the required format in python**

**------------------------------------------------------------------------------------------------------------------------------------**

**NOTE::AS json file's structure closely relates to a python dictionary so my idea was to  treat the files as such and as the output of our json file had the titles ,(which now became our key values in python dictionary) as the keys**

**First upon using the API we get 100 zip folders each containg a .json file and some .xlsx file containing the tables

**Upon verifying the .xlsx tables of each zip file I came to know that the last but one was an empty file so I had to remove that

**First I unzipped each file and extracted all the .json files(and renaming them by appending the index of the file being read as required) and the tables

**Then as mentioned above I removed those unwanted garbage tables

**Now I appended all the tables and created a large table for all the 100 files and created a large table that shall conatin info about the price ,quantituy and rate of an entity

**Now coming to the text parsing part ,from the extracted .json files,which are now being treated as python dictionary(This was done using json.load):
  Our key values are the title,from them I extracted the columns using RegEx module in python as follows::
    <img width="959" alt="Screenshot 0005-07-29 at 14 10 51" src="https://github.com/KewangZhili/Projects/assets/111041497/2c2cb357-817f-40a5-b4e8-e33f06548025">

  Then using namedtuple module,I created tuples as follows:: and then went on iterating for 100 files and appending these tuples
    

<img width="891" alt="Screenshot 0005-07-29 at 14 11 50" src="https://github.com/KewangZhili/Projects/assets/111041497/9a2bb027-b677-4958-88a8-98ea91b3d4af">

  Finally the above created table into a pandas dataframe and did some fine tuning such as removing the indices,(as required in the guidelines) and converting the values to int etc...
**------------------------------------------------------------------------------------------------------------------------------------**

        ****And at last converted the dataframe into a csv file as "ExtractedData-4.csv"****

