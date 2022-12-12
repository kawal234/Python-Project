# Python-Project
contacts = {"KAWAL":7263736569,"ISHANT":7464533887,"NIKHIL":7564890342,"DEEPAK":7688595885,"SACHIN":9484673836,"FAZIL":7973694726,"SHAHNAWAZ":9375846853,"YASH":8467354826,"ISHITA":9379635959,"ANSHIKA":8946725296,"DIVYANSHI":8964869365,"AMLAN":8625863852,"AISHWARY":8658348568}
# Searches the dictionary and prints the key value pair incase the key isn't  present, it adds the dict and print it
def single_search():
    name = input("Enter the name of the contact you wish to search for: ").upper()
    if name in contacts:
        print(f"\n{name}:{contacts[name]}")
    else:
        b = input("\nNo such contact found \nIf you wish to add one, type'Y' else type 'No':").lower()
        if b == "yes":
            new_contacts(name)
            print(f"{name}:{contacts[name]}")
        elif b== "no":
            pass
        else:
            print("Enter either yes or no ")

# Searches the dictionary and prints multiple key value pair and incase any key isn't present, it adds it to the dict and prints it along with the others 
def multiple_search():
    result = {}
    s1 = []
    s=0
    name1 = input("Enter the names of the contacts seperated by commas:").split(",")
    for i in name1:
        i = i.upper()
        if i in contacts:
            result[i]=contacts[i]
        else:
            s1.append(i)
            s+=1
    if s>0:
        c = input(f"\nCouldn't find contacts {s1}.\nDo you wish to add them? Enter YES or NO:")
        if c=="yes":
            for i in s1:
                new_contacts(i)
                if i in contacts:
                    result[i]=contacts[i]
            print()
            print(result)
        elif c=="no":
            print()
            if result=={}:
                pass
        else:
            print("Please Verify it Properly")
    else:
        print()
        print(result)   
# adds new contact every time its called
def new_contacts(contact_name):
    print()
    contact_number = int(input("Enter their contact number:"))
    contacts[contact_name]=contact_number

str1=("Welcome To the Contact List of XYZ Company")
print(str1.center(100))
choice = int(input("\n\nWould you like to:\n\n1.Search for a single contact\n\n2.List all the contacts\n\n3.Search for multiple contacts\n\nEnter your choice:"))   
if choice == 1:
    single_search()
elif choice==2:
    print()
    print(contacts)
elif choice==3:
    multiple_search()
else:
    print("Choose from the given options!")   


print("\n\nThank You For Using Our System.")
