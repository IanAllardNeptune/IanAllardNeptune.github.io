---
layout: post
title: Digimon Project
subtitle: 
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [books, test]
author: Ian Allard-Neptune
---

# The Digimon Project:

Overall, I did the majority of this project on my own with the help of Ms. Feng and lots of Google searches for various errors or questions.

## Question 1: 
[Version of Ms. Feng's Penguin code that I used]([www.github.com](https://github.com/ifenghm/art-of-data-code/blob/6de6f067c8c39462248c60ce927fbe7b7c7b779e/unit1/lessons/penguins.py))  
For the first question, I used the basis of Ms. Feng's code from the Penguin.py project, which essentially took a dataset and organized it into a new dictionary. I manipulated this code only to have the keys I needed to answer this first question: "Lv 50 HP", and removed the parts of her code that took averages of the values. Using Ms. Feng's code as a basis this question was pretty simple and I did not run into too many problems. 

#### Here is the code:

    def question1():
        with open("/Users/ianallard-neptune/Art_Of_Data/datasets/DigimonDataset/DigiDB_Digimonlist.csv", "r") as f:
        data = csv.DictReader(f)
        Digimon_data = {}  

        for row in data:
            if row["Digimon"] not in Digimon_data:
                
                Digimon_data[row["Digimon"]] = {
                    "Lv 50 HP": [],
                }  

            if row["Lv 50 HP"] != "NA":
                Digimon_data[row["Digimon"]]["Lv 50 HP"].append(
                    float(row["Lv 50 HP"])
                )

        for Digimon in Digimon_data:
            Lv_50_HP = Digimon_data[Digimon]["Lv 50 HP"]
            Digimon_data[Digimon]["Lv 50 HP_average"] = sum(Lv_50_HP) / len(
                Lv_50_HP
            )

        maxc = max(Digimon_data, key=lambda x: Digimon_data[x]["Lv 50 HP_average"])
        print(
            f"1. The Digimon with the largest avg HP is: {maxc} at {Digimon_data[maxc]['Lv 50 HP_average']}"
        )

## Question 2: 

I thought this question was the easiest of the three, and I was able to solve it entirely on my own. While I did not reference specific code in solving this function, a similar solution was possible for one of the Penguin.csv questions with the method of counting through each value of a certain key-value.

#### Here is the code:

    def question2(attribute, value) :
     with open("/Users/ianallard-neptune/Art_Of_Data/datasets/DigimonDataset/DigiDB_Digimonlist.csv", "r") as f:
            data = csv.DictReader(f)
            count = 0
        
        for Digimon in data:
            if Digimon[attribute] and Digimon[attribute] == value:
                count = count + 1
        print("2. The amount of " + str(attribute) + " with " + str(value) + " is: "+ str(count))

## Question 3:

This question was by far the most difficult of the three questions, and it took up most of my time for this project. My first solution to the problem was a hacky piece of code that essentially hard-coded assumptions of the dataset. 

Here is the first _"hacky"_ attempt:

    question3()


     def digimonTeam() :
         with open("/Users/ianallard-neptune/Art_Of_Data/datasets/DigimonDataset/DigiDB_Digimonlist.csv", "r") as f:
             data = csv.DictReader(f)
             digimonAmt = 0
             teamNames = ""
      
         for Digimon in data:
  
             if int(Digimon["Memory"]) < int("6") and int(Digimon["Lv50 Atk"]) > int("100") and digimonAmt < 3 :
                if digimonAmt == 0:
                     teamNames = teamNames + Digimon["Digimon"]
                     digimonAmt = digimonAmt + 1
                else :
                    teamNames = teamNames + ", " + Digimon["Digimon"]
                    digimonAmt = digimonAmt + 1
          
         print("3. The team is: " + teamNames)

As you can see, the code depends upon their Digimon, which have less than 6 memory and more than 100 atk. This assumption would not have always worked with a different dataset of digimon.  For example: If there was only one digimon that had >200 atk with 10 memory and all of the other digimon had <3 memory but an attack ~50. In this case there is a team that satisfies the question, but the constraints placed in the if statement would not catch this answer.  The other glaring issue with this piece of code is that it simply finds the first team that answers the question and not the best team. For both of these reasons, I chose to rewrite the code.

Repeated errors I ran into: 
([https://stackoverflow.com/questions/19991591/typeerror-float-object-is-not-subscriptable])
([https://stackoverflow.com/questions/6077675/why-am-i-seeing-typeerror-string-indices-must-be-integers])

