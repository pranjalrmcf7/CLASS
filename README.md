# CLASS
Inheritance

class Employee:
	raise_amount = 1.02

	def __init__(self,first,last,pay):
		self.first = first
		self.last = last
		self.pay = pay
		self.email = first + '.' + last +'@gmail.com'

	def fullname(self):
	    print(self.first ,self.last) 

	def apply_raise(self):
		self.pay = int(self.pay * self.raise_amount)


class Developer(Employee):
	raise_amount = 1.10

	def __init__(self,first,last,pay,prog_lang):
		super().__init__(first,last,pay)
		self.prog_lang = prog_lang


class Manager(Employee):
	raise_amount = 1.05

	def __init__(self,first,last,pay,employees):
		super().__init__(first,last,pay)
		self.employees = employees

	def add_emp(self,emp):
		if emp not in self.employees:
			self.employees.append(emp)

	def remove_emp(self,emp):
		if emp in self.employees:
			self.employees.remove(emp)

	def print_emp(self):
		for emp in self.employees:
			print(emp.fullname())



dev_1 = Developer('Pranjal','RMCF',140000,'Python')
dev_2 = Developer('James','Dean',115000,'Java')
dev_3 = Developer('Michael','Jackson',90000,'Ruby')
dev_4 = Developer('Daniel',"Radcliffe",85000,'C')

mgr_1 = Manager('Steven','Spielberg',120000,[dev_1,dev_4])
mgr_2 = Manager('James','Cameron',110000,[dev_2,dev_3])

#print(dev_1.email)
mgr_1.print_emp()
#mgr_1.add_emp(dev_3)
#mgr_1.print_emp()
#print(dev_4.prog_lang)
#print(isinstance(dev_4,Manager))
#print(issubclass(Developer,Manager))
