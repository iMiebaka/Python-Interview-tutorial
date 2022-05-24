# 1 ) Even odd number

        a = int(input("Enter the numbmer :"))
        if a % 2 == 0:
            print("Even Number")
        else:
            print("Odd Number")

# 2 Factorial number

        a = int(input("Enter the number"))
        factorial = 1
        for i in range(1,a+1):
            factorial = factorial*i
        print(factorial)
        
# 3 ) Reverse string

        a = input("Enter the string :")
        data = a.split()
        print(" ".join(data[::-1]))
        
# 4 ) 
