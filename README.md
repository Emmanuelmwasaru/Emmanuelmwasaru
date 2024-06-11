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
# Install necessary packages
install.packages("tm")
install.packages("textstem")

# Load libraries
library(tm)
library(textstem)

# Sample text
text <- "This is a sample text. It is used for demonstrating text summarization in R. This text contains multiple sentences. Text summarization is a process of creating a short and concise version of a longer document."

# Create a Corpus
docs <- Corpus(VectorSource(text))

# Preprocessing
docs <- tm_map(docs, content_transformer(tolower))
docs <- tm_map(docs, removePunctuation)
docs <- tm_map(docs, removeNumbers)
docs <- tm_map(docs, removeWords, stopwords("english"))
docs <- tm_map(docs, stripWhitespace)
docs <- tm_map(docs, lemmatize_strings)

# Convert to a Document-Term Matrix
dtm <- DocumentTermMatrix(docs)

# Calculate term frequency
term_freq <- colSums(as.matrix(dtm))
term_freq <- sort(term_freq, decreasing = TRUE)

# Display the most frequent terms
term_freq

# Summarization (basic approach by taking top n sentences)
n <- 2
sentences <- unlist(strsplit(text, "(?<=[.!?])\\s+", perl = TRUE))
scores <- sapply(sentences, function(sentence) sum(term_freq[unlist(strsplit(sentence, " "))]))
top_sentences <- sentences[order(scores, decreasing = TRUE)][1:n]

# Concatenate the summary sentences
summary <- paste(top_sentences, collapse = " ")
summary

