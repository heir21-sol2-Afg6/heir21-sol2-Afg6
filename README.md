import re



phone = input()



test = re.fullmatch(r'^((8|\+7)[\- ]?)?(?\d3
?[\- ]?)?[\d\- ]{7,10}$', phone)

if not test:

    print('Неправильный номер телефона')

    exit(1)



print(phone, type(phone))

phone_book = [phone]

phone_book += ['8(495)430-23-97', '+7-4-9-5-43-023-97', '4-3-0-2-3-9-7',

               '8-495-430', '+79185238495']

print('phone_book =\t', phone_book, type(phone_book))



'''for s in phone_book:

    print(s, type(s))

'''



phone_book_new = [s.replace('-', '').replace('(', '').replace(')', '')

                  for s in phone_book]

'''for s in phone_book:

    # print(s, type(s))

    phone_book_new.append(s.replace('-', '').replace('(', '').replace(')', ''))

'''

for i in range(len(phone_book_new)):

    # print(i, type(i))

    if len(phone_book_new[i]) == 7:

        phone_book_new[i] = '+7495' + phone_book_new[i]

    elif len(phone_book_new[i]) == 10:

        phone_book_new[i] = '+7' + phone_book_new[i]

    elif phone_book_new[i][0] == '8':

        phone_book_new[i] = '+7' + phone_book_new[i][1:]



print('phone_book_new =', phone_book_new, type(phone_book_new))



s1 = phone_book_new[0]

for s in phone_book_new[1:]:

    if s1 == s:

        print('YES')

    else:

        print('NO')
--->
