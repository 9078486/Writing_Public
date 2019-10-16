import csv

list_category = [] 

with open('wacai_2019-01-01_2019-10-12.csv', 'r') as f:
	reader = csv.reader(f)
	for item in reader:
		list_category.append(item[0] + '-' + item[1]) 

print(sorted(set(list_category)))