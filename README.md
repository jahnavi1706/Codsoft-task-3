import random
import string

def generate_password(length):
    """Generates a random password of a specified length.

    Args:
        length: The desired length of the password.

    Returns:
        A randomly generated password string.
    """
    characters = string.ascii_letters + string.digits + string.punctuation
    password = ''.join(random.choice(characters) for i in range(length))
    return password

def main():
    """Main function to run the password generator."""
    print("Welcome to the Password Generator!")

    while True:
        try:
            desired_length = int(input("Enter the desired length of the password: "))
            if desired_length <= 0:
                print("Please enter a positive number for the password length.")
            else:
                break
        except ValueError:
            print("Invalid input. Please enter a number.")

    generated_password = generate_password(desired_length)
    print(f"Your generated password is: {generated_password}")

if __name__ == "__main__":
    main()
