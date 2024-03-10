# YAML - YAML AIN'T MARKUP LANGUAGE

YAML is a human readable data serialization language that is often used for configuration files
Yaml is for data and boy document because markup languages only stores document

### YAML USED FOR

one of the most common uses for yamkl is to create a configuration file . its recommended that configuration files be written in YAML rather than JSON in addition to its use it is used in ANSIBLE
Yaml is used for kubernetes resources and deployment
Yaml file can be added to sorce control such as github etc

Yaml is case sensitive apple and Apple is different thing
"""Yaml file extension is .yaml or .yml """

## Benfits of YAML
-its Easy to Read and simple to Understand 
-Easily convertable to JSON and XML
-It Has Strict Intetdation like Python
-More Powerful When Representing Complex data

## key Value Pair
```
name:"Ramkumar Nadar"
name:"Nishant Ghadigaonkar"
name:"Shubham Tambitkar"
```


## list 
``` 
-Mumbai
-Chennai
-Delhi
```
## Block Style 
```
citie:
 -Mumbai
 -Chennai
 -Delhi
```

```
  --- is used to seperate document
  ... is mean document ended
```

# Data Types
## string Variables 
```
myself : Ramkumar Nadar 
fruit : "Apple"
job: 'Software Developer Trainee'
```

### defining a multiline string variable message using the folded style > and then redefining it as a string using the !!str tag.
```
message: >
this document created
while learning yaml 

```
## defining variables
```message: !!str this document created while learning yaml 

number: 76200
```
## specifying Types
```
zero: !!int 0
positiveNumber: !!int 12
negativeNumber: !!int -85

not a num: .nan
```

## floating number
```
marks: !!float 566.9
surname: !!null
~: this a null key 

exponential number: 6.023E


#date and time
date: !!timezone  2023-12-14
```
# Advanaced Data Types
## sequence
```

students: !!seq
 -marks
 -name
 -rollno

 cities: [new delhi, mumbai]
```

## some of the key of the sequence will be empty that iws known as sparse sequence
### sparse seq
```sparse seq:
 -hey
 -hello
 -
 -Null
 -sup
```
## nested sequence
```
-
 - mango
 - apple
 - banana
-
 - marks
 - roll num
 - date
```
## key : value pairs are called maps
!!map 

## nested mapping : map within a map
```
name: Ramkumar Nadar
role: 
 age: 24
 job: student
```
### same as above
```
name: Ramkumar
role: { age: 24, job: student} 
```
# pairs - key may have duplicate values
```
pair example: !!pairs
 -job: student
 -job: teacher
```
### same as above 
``` 
pair example: !!pairs [job: student, job: teacher]
```
## set
### !!set will allow to have a unique values
```
name: !!set
 ?Ramkumar
 ?Shubham
 ?Nishant

```
## dictionary !!omap
```
people: !!omap
 - Ramkumar:
    name: Ramkumar
    age: 24
 - Nishant:
    name: Nishant
    age: 24
 - Shubham:
    name: Shubham Tambitkar
    age: 24
```
### reusing some properties using anchors
### anchors means what to copy and where to copy
```
likings: @likes
 fav fruit: mango 
 dilikes: grapes

person:
 name: Ramkumar Nadar
 fav fruit: mango 
 dilikes: grapes

person1:
 name: Ramkumar Nadar
 <<: *likes
```
### overriding the values 
```
person2:
 name: Ramkumar Nadar
 <<: *likes
 dislikes: berries
```