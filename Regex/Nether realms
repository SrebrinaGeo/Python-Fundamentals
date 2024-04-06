import re


def get_demon_health(text: str) -> int:
    health = 0
    match_pattern = re.findall(r"[^0-9\*\+\-\/\.]", text)
    for letter in match_pattern:
        health += ord(letter)
    return health


def calculate_damage(text: str) -> float:
    multiply_divide = re.findall(r"[\/\*]", text)
    number_matches = re.findall(r"(\-?[0-9]+[\.0-9]*)", text)
    base_damage = sum([float(i) for i in number_matches])
    for operation in multiply_divide:
        if operation == "*":
            base_damage *= 2
        else:
            base_damage /= 2
    return base_damage


demons = re.sub(" ", "", input()).split(",")
for demon in sorted(demons):
    health = get_demon_health(demon)
    damage = calculate_damage(demon)
    print(f"{demon} - {health} health, {damage:.2f} damage")
