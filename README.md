# HealthManagementSystem

				
Customer = { 0 : 'New User' ,  1 : 'Ankit' ,  2 : 'Nilesh' ,  3: 'Shivam' }	
Action = { 1 : 'Exercise' , 2 : 'Diet' }

def getdate():
	import datetime
	return datetime.datetime.now()
	
def log():
	with open(Customer[P] + '-' + Action[b] + '.txt', 'a') as f:
		ip = 'y'
		while ip == 'y' :
			print('Enter', Action[b], ': ')
			item = input()
			f.write("[" + str(getdate()) + "]: " + item + "\n")
			print('Routine Updated!')
			print('Would you like to log in more ' + Action[b] + ' routine')
			ip= input('[y/n]: ')
		print('Your ' + Action[b] + ' routine has been updated.')

def retrive():
	print(Customer[P] + '-' + Action[b] + ' Report: \n')
	with open(Customer[P] + '-' + Action[b] + '.txt', 'r') as f:
		print(f.read())
		
				
print("Please confirm your Identity: ")
for key, value in Customer.items():
	print('Press', key, 'for', value, '\n', end="")
	
try:
	P = int(input( ))
	if P != 0:
		print("Hello! " + Customer[P])
	else:
		k = int(input("Enter next int key: "))
		new = input("Enter your Name: ")
		c = dict([(k , new)])
		Customer.update(c)
			
	a = int(input("What would you like to do: \n 1.Log \n 2.Retrieve\n"))
	if a == 1:
		for key, value in Action.items():
			print('Press', key, 'to log', value, '\n', end="")
		b = int(input( ))
		log()
		
	elif a == 2:
		for key, value in Action.items():
			print('Press', key, 'to retrive', value, '\n', end="")
		b = int(input( ))
		retrive()
except Exception as e:
	print('Please Enter valid input')
	
