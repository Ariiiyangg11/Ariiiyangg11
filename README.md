import matplotlib.pyplot as plt

num_candidates = int(input("Enter the number of candidates: "))

names = []
votes = []

for i in range(num_candidates):
    name = input(f"Enter the name of candidate {i+1}: ")
    vote = int(input(f"Enter the number of votes for {name}: "))
    names.append(name)
    votes.append(vote)

winner_index = votes.index(max(votes))
winner = names[winner_index]

print(f"Winner: {winner}")

# Bar chart
plt.figure(figsize=(10, 5))  # Adjust figure size if needed
plt.bar(names, votes)
plt.xlabel("Candidates")
plt.ylabel("Number of Votes")
plt.title("Election Results")
plt.show()


# Pie chart
plt.figure(figsize=(8, 8))
plt.pie(votes, labels=names, autopct='%1.1f%%', startangle=140)
plt.title("Candidate Ratings in Percentage")
plt.axis('equal')  # Equal aspect ratio ensures that pie is drawn as a circle.
plt.show()
