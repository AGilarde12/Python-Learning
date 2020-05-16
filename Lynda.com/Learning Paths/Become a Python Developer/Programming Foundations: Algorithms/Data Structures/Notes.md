#Linked Lists_Start#

#Classes Notes:
#Lets say I want to create a game and organize weapons I create under a weapon class
#even though there are giong to be multiple different weapons, i know there 
#Will be a couple of similarites between them, such as name, value, etc

class Weapon:
    def __init__(self, name, description, power, value):
        self.name = name
        self.description = description
        self.power = power
        self.value = value

#By doing this you are basically saying " I know all of my weapons will have these parameters in common"
#A name, a description, a power and a value

#But what are __init__ and self????
#self is like a placeholder for your actual weapons
#for example, if you create this:
sword = Weapon(name='sword', description = 'a regular sword', power = 10, value = 10)

    


#Node Class
class Node(object):
    def __init__(self, val):
        self.val = val
        self.next = None #Indicates single linked list

    def get_data(self):
        return self.val

    def set_data(self, val):
        self.val = val

    def get_next(self):
        return self.next

    def set_next(self, next): #Grab the next link in the list
        self.next = next

class LinkedList(object):
    def __init__(self, head=None):
        self.head = head
        self.count = 0

    def get_count(self):
        return self.count
    
