https://sites.google.com/site/marianneclausel/home/lectures-2025-2026/m1-nlp-statistics?authuser=0


# Sets the random seed so that the random numbers generated are reproducible.
# Using the same seed will always give you the same random values.
np.random.seed(10)
# generates 150,000 random values from a Poisson distribution with mean 35,
# Then adds 18 to every value. This simulates ages with an average around 35 + 18 = 53 years old.
population_ages1 = stats.poisson.rvs(loc=18, mu=35, size=150000)
# Generates 100,000 random values from a Poisson distribution with mean 10,
# Then adds 18 to every value. This simulates ages with an average around 10 + 18 = 28 years old.
population_ages2 = stats.poisson.rvs(loc=18, mu=10, size=100000)


population_ages = np.concatenate((population_ages1, population_ages2))

population_ages.mean()


np.random.seed(6)
sample_ages = np.random.choice(a= population_ages, size=500)            # Sample 1000 values

print ( round(sample_ages.mean(),0) )                         # Show sample mean

round(population_ages.mean() - sample_ages.mean() ,1)  # Check difference between means

population_students = (["Humanities"]*500000) + (["Sciences"]*300000) +\
                   (["Medecine"]*200000) + (["Economics"]*400000) +\
                   (["other"]*30000)

random.seed(10)
demo_sample = random.sample(population_students,1000)   # Sample 1000 values

for students in set(demo_sample):
    print(students + " proportion estimate:" )
    print(demo_sample.count(students)/1000)
                   
