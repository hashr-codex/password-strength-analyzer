import string

def analyze_password(password):
    score = 0
    feedback = []

    if len(password) >= 8:
        score += 20
    else:
        feedback.append("Password should be at least 8 character long.")

    if len(password) >= 12:
        score += 10

    if any(c.islower() for c in password):
        score += 15
    else:
        feedback.append("Add lowercase letters.")

    if any(c.isupper() for c in password):
        score += 15
    else:
        feedback.append("Add uppercase letters.")

    if any(c.isdigit() for c in password):
        score += 15
    else:
        feedback.append("Add numbers.")

    if any(c in string.punctuation for c in password):
        score += 15
    else:
        feedback.append("Add special characters.")

    return score, feedback

def strength_label(score):

    if score >= 85:
        return "Very Strong"
    elif score >= 65:
        return "Strong"
    elif score >= 40:
        return "Medium"
    else:
        return "Weak"
    
if __name__ == "__main__":
    print("Password Strength Analyzer\n")

    password = input("Enter a password to analyze: ")

    score, feedback = analyze_password(password)
    label = strength_label(score)


    print("\nresult")
    print("-" * 20)
    print(f"Strength : {label}")
    print(f"score    : {score}/100")

    if feedback:
        print("\nSuggestions:")
        for tip in feedback:
            print(f"- {tip}")
    else:
        print("\nExcellent password!")