---
layout: post
title: Digimon Project
subtitle: 
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/thumb.png
share-img: /assets/img/path.jpg
tags: [books, test]
author: Sharon Smith and Barry Simpson
---

# The Digimon Project:

Overall, I did the majority of this project on my own with the help of Ms. Feng and lots of Google searches for various errors or questions.

## Question 1: 
[Version of Ms. Feng's Penguin code that I used]([www.github.com](https://github.com/ifenghm/art-of-data-code/blob/6de6f067c8c39462248c60ce927fbe7b7c7b779e/unit1/lessons/penguins.py))
For the first question, I used the basis of Ms. Feng's code from the Penguin.py project, which essentially took a dataset and organized it into a new dictionary. I manipulated this code only to have the keys I needed to answer this first question: "Lv 50 HP", and removed the parts of her code that took averages of the values.

'''Python
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
'''


Repeated errors I ran into: 
([https://stackoverflow.com/questions/19991591/typeerror-float-object-is-not-subscriptable])
([https://stackoverflow.com/questions/6077675/why-am-i-seeing-typeerror-string-indices-must-be-integers])

The truth is that no one else can definitively know the path we are here to walk. It’s tempting to listen—many of us long for the omnipotent other—but unless they are genuine psychic intuitives, they can’t know. All others can know is their own truth, and if they’ve actually done the work to excavate it, they will have the good sense to know that they cannot genuinely know anyone else’s. Only soul knows the path it is here to walk. Since you are the only one living in your temple, only you can know its scriptures and interpretive structure.

At the heart of the struggle are two very different ideas of success—survival-driven and soul-driven. For survivalists, success is security, pragmatism, power over others. Success is the absence of material suffering, the nourishing of the soul be damned. It is an odd and ironic thing that most of the material power in our world often resides in the hands of younger souls. Still working in the egoic and material realms, they love the sensations of power and focus most of their energy on accumulation. Older souls tend not to be as materially driven. They have already played the worldly game in previous lives and they search for more subtle shades of meaning in this one—authentication rather than accumulation. They are often ignored by the culture at large, although they really are the truest warriors.

A soulful notion of success rests on the actualization of our innate image. Success is simply the completion of a soul step, however unsightly it may be. We have finished what we started when the lesson is learned. What a fear-based culture calls a wonderful opportunity may be fruitless and misguided for the soul. Staying in a passionless relationship may satisfy our need for comfort, but it may stifle the soul. Becoming a famous lawyer is only worthwhile if the soul demands it. It is an essential failure if you are called to be a monastic this time around. If you need to explore and abandon ten careers in order to stretch your soul toward its innate image, then so be it. Flake it till you make it.
