#The below method calculates and gives the result in the form of "dictonary" including percentages.
dict = {}
with open("C:/Users/user/Desktop/python/ecoli.fasta", 'r') as f:    
    for line in f:
        if line.startswith(">"):
            pass
        else:
            line = line.strip()
            for i in line:
                if i in dict:
                  dict[i] += 1
                else:
                   dict[i] = 1
    print(dict)
            
    for i in dict:
        b = (f"{(round((dict[i] / sum(dict.values()) * 100), 2))}%")
        print(i, dict[i], b)
