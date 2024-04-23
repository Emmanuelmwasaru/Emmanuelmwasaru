- 👋 Hi, I’m @Emmanuelmwasaru
- 👀 I’m interested in Biostatistics 
- 🌱 I’m currently learning Biostatistics 
- 💞️ I’m looking to collaborate on data science 
- 📫 How to reach me on Facebook @Emmanuel Mwasaru 
- 😄 Pronouns: He
- ⚡ Fun fact: Coolkid

<!
Emmanuelmwasaru/Emmanuelmwasaru is a ✨ special ✨ repository because its `README.md` (this file) appears on your GitHub profile.
You can click the Preview link to take a look at your changes.
--->
npm install
import random

def generate_random_numbers(count, start, end):
    random_numbers = []
    for _ in range(count):
        random_numbers.append(random.randint(start, end))
    return random_numbers

if __name__ == "__main__":
    count = 100  # Number of random numbers to generate
    start_range = 1  # Start of the range
    end_range = 1000  # End of the range

    random_numbers = generate_random_numbers(count, start_range, end_range)
    print("Generated Random Numbers:", random_numbers)
