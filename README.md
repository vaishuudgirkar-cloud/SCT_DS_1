import matplotlib.pyplot as plt
import seaborn as sns
import pandas as pd

# Sample data: Gender distribution in a population
data = {
    'Gender': ['Male', 'Female', 'Other'],
    'Count': [5200, 4800, 200]
}

df = pd.DataFrame(data)

# Set the style for attractiveness
sns.set(style="whitegrid")

plt.figure(figsize=(8, 6))
ax = sns.barplot(x='Gender', y='Count', data=df, palette='viridis')

plt.title('Gender Distribution in Population', fontsize=16)
plt.xlabel('Gender', fontsize=14)
plt.ylabel('Count', fontsize=14)

# Add value labels on bars
for p in ax.patches:
    ax.annotate(f'{int(p.get_height())}', 
                (p.get_x() + p.get_width() / 2., p.get_height()), 
                ha='center', va='center', fontsize=12, color='black', xytext=(0, 10),
                textcoords='offset points')

plt.tight_layout()
plt.show()
