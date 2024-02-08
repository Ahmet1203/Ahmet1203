import random

def get_user_choice():
    user_choice = input("Taş, Kağıt, Makas? ").strip().lower()
    while user_choice not in ["taş", "kağıt", "makas"]:
        print("Geçersiz seçim. Lütfen tekrar deneyin.")
        user_choice = input("Taş, Kağıt, Makas? ").strip().lower()
    return user_choice

def get_computer_choice():
    choices = ["taş", "kağıt", "makas"]
    computer_choice = random.choice(choices)
    return computer_choice

def determine_winner(user_choice, computer_choice):
    if user_choice == computer_choice:
        return "Berabere!"
    elif (user_choice == "taş" and computer_choice == "makas") or (user_choice == "kağıt" and computer_choice == "taş") or (user_choice == "makas" and computer_choice == "kağıt"):
        return "Kazandınız!"
    else:
        return "Bilgisayar Kazandı!"

def main():
    user_choice = get_user_choice()
    computer_choice = get_computer_choice()
    print(f"Siz: {user_choice}")
    print(f"Bilgisayar: {computer_choice}")
    result = determine_winner(user_choice, computer_choice)
    print(result)

if __name__ == "__main":
    main()
