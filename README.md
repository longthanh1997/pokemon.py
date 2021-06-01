import random
import pypokedex


#main function 

def main():
    
    
    
    
    
    player1_pokemon = input("P1 : choose your pokemon !!")
    p=pypokedex.get(dex=random.randint(0,322))
    player2_pokemon = p.name
  
    print(" P1 picked " + player1_pokemon + ","+" P2 picked " + player2_pokemon)
    
    # print thong bao 
    print("Prepair your self!! ")
    
    #call battle function 
    battle(player1_pokemon,player2_pokemon)
    
 
 
#battle funcion 
def battle(player1_pokemon,player2_pokemon) :
    #attack 
    attack=["Normal attack","Special attack"]
    #pokemon HP 
    P1health = 100
    P2health = 100 
    #damage of Normal atk and Special atk 
    atkA  = 30
    defA = 10
    spatkA = 35
    elemental_multiplyA = 0.2
    spdefA=15
    expA=32.2
    
    atkB  = 40
    defB = 15
    spatkB = 45
    elemental_multiplyB = 0.3
    spdefB=20
    expB=64.4
    #pokemonlist
    i=1
    pokemon_list1=["Charizard","Blastoise","Y","N"]
    pokemon_list2=["Nidoking","Gengar","Y","N"]
    # check to see if the war still happening
    fight = True
    while fight ==True:
        print(player1_pokemon, " 1. normal attack , 2. special attack ")
        #P1 phase
        battle = int (input("P1 select to attack")) 
        #abcxyz
        
        if battle == 1:
            P2health -=(atkA-defB)
            print("P1's pokemon did ",(atkA-defB)," damage" )
        elif battle ==2:
            P2health -= ((spatkA*elemental_multiplyB)-spdefB)
            print("P1's pokemon did ",((spatkA*elemental_multiplyB)-spdefB)," damage" )
        
        #P2 phase 
        print(player2_pokemon, " 3. normal attack , 4. special attack ")
        P2_power=int(input("P2 select to attack!!!"))
        
        if P2_power == 3:
            P1health -=(atkB-defA)
            print("P2's pokemon did ",(atkA-defB)," damage" )
        elif P2_power == 4:
            P1health -= ((spatkB*elemental_multiplyA)-spdefA)
            print("P2's pokemon did ",((spatkB*elemental_multiplyA)-spdefA)," damage" )
        print(player1_pokemon," is on ", P1health ," health and ",player2_pokemon," is on ",P2health,"!\n ==================================")
        if P2health <=0:
            print(player2_pokemon," HAS DIED ",player1_pokemon," has gained ",expB," !!!!!")
            fight=False
            print("P2 pls switch your pokemon Y/N? ")
            for x in pokemon_list2:
                print(i,".",x)
                i+=1
            found = False
            while found == False:
                player2_pokemon = input("do you want to switch pokemon")
                for x in pokemon_list2:
                    if (player2_pokemon == x ):
                        found = True
                        player2_pokemon=input ("P2 : what pokemon do you want to switch ?? ")
                        switch2= int (input("P2 : 1.Nidoking    2.Gengar")) 
                        if switch2 ==1 :
                            print("P2 selected Nidoking")
                            player2_pokemon = ["Nidoking"]
                            P2health=100
                          
                                                             
                        if switch2 ==2:
                            print("P2 selected Gengar")
                            player2_pokemon=["Gengar"]
                            
                            P2health=100    
                    if found == False:
                        print("wrong selecting,  pls try again dude !!!! ")
                        
                
        elif P1health<=0:
            print(player1_pokemon," HAS DIED ",player2_pokemon," has gained ",expA," !!!!!")
            fight=False
            print("P1 pls switch your pokemon ")
            for x in pokemon_list1:
                print(i,".",x)
                i+=1
            found = False
            while found == False:
                player1_pokemon = input("do you want to switch pokemon ??")
                for x in pokemon_list1:
                    if (player1_pokemon == x ):
                        found = True
                    
                        switch1= int (input("P1 : 1.Charizard    2.Blastoise")) 
                        if switch1 ==1 :
                            print("P2 selected Charizard")
                            player1_pokemon = ["Charizard"]
                            P1health=100
                          
                                                             
                        if switch1 ==2:
                            print("P1 selected Blastoise")
                            player1_pokemon=["Blastoise"]
                            
                            P1health=100    
                        
                         
                      
                    if found == False:
                        print("wrong selecting,  pls try again dude !!!! ")
            


              
         
main()           
        
         
         
        
