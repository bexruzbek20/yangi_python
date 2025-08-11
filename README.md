import random 

eni = 13
boyi = 9 
oyinchi = '👤'

x = random.randint(0, eni-1)
y = boyi - 1

tuzoq_joylari = set()

while len(tuzoq_joylari) < 4:
    tx = random.randint(0, eni-1)
    ty = random.randint(0, boyi-1)
    if (tx, ty) != (x, y):
        tuzoq_joylari.add((tx, ty))
    else:
        print('tuzoq')

print('👤 oyinchi korinishi')
print('💀 agagr siz tuzoqqa tussangiz yutqazasiz')
print('Agar tuzoqqa tushmasdan oxiriga chiqasangiz yutasiz')

def chiz():
    for j in range(boyi):
        for i in range(eni):
            if i == x and j == y:
                print(oyinchi, end="")
            else:
                print('.',end="")
        print()
while True:
    chiz()
    harakat = input('Harakat qilish uchun (w/a/s/d) chiqish (q) : ').lower()
    if harakat == 'a' and x > 0:
        x -= 1
    elif harakat == 'w':
        if y == 0:
            print('siz yutdingiz')
            break
        else:
            y -= 1
    elif harakat == 's' and y < boyi - 1:
        y+= 1
    elif harakat == 'q':
        print('Chiqildi')
        break
    if (x,y) in tuzoq_joylari:
        print('Siz tuzoqqa tushdingiz 💀')
        break
    else:
        print('bu yerda tuzoq yoq yuravering')
