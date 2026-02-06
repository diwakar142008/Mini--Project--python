** start of main.py **

def validate_isbn(isbn, length):
    # Check for invalid characters
    if length == 10:
        if not (isbn[:-1].isdigit() and (isbn[-1].isdigit() or isbn[-1] == 'X')):
            print('Invalid character was found.')
            return
    else:
        if not isbn.isdigit():
            print('Invalid character was found.')
            return

    # Check ISBN length
    if len(isbn) != length:
        print(f'ISBN-{length} code should be {length} digits long.')
        return

    main_digits = isbn[:-1]
    given_check_digit = isbn[-1]

    main_digits_list = [int(d) for d in main_digits]

    if length == 10:
        expected = calculate_check_digit_10(main_digits_list)
    else:
        expected = calculate_check_digit_13(main_digits_list)

    if given_check_digit == expected:
        print('Valid ISBN Code.')
    else:
        print('Invalid ISBN Code.')


def calculate_check_digit_10(main_digits_list):
    total = 0
    for i, digit in enumerate(main_digits_list):
        total += digit * (10 - i)

    result = 11 - (total % 11)

    if result == 11:
        return '0'
    elif result == 10:
        return 'X'
    else:
        return str(result)


def calculate_check_digit_13(main_digits_list):
    total = 0
    for i, digit in enumerate(main_digits_list):
        if i % 2 == 0:
            total += digit
        else:
            total += digit * 3

    result = 10 - (total % 10)

    if result == 10:
        return '0'
    else:
        return str(result)


def main():
    user_input = input('Enter ISBN and length: ')

    if ',' not in user_input:
        print('Enter comma-separated values.')
        return

    values = user_input.split(',')

    if len(values) != 2:
        print('Enter comma-separated values.')
        return

    isbn = values[0]

    try:
        length = int(values[1])
    except:
        print('Length must be a number.')
        return

    if length != 10 and length != 13:
        print('Length should be 10 or 13.')
        return

    validate_isbn(isbn, length)


# main()   # ✅ COMMENTED OUT AS REQUIRED


** end of main.py **

