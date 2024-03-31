              class Employee:
                  def __init__(self, name, address, mobile, salary, profile, joining_date):
                      self.name = name
                      self.address = address
                      self.mobile = mobile
                      self.__salary = salary
                      self.profile = profile
                      self.joining_date = joining_date
                  
                  def employee_details(self):
                      print(self.name)
                      print(self.address)
                      print(self.mobile)
                      print(self.__salary)
                      print(self.profile)
                      print(self.joining_date)
              
              class HR(Employee):
                  def __init__(self, name, address, mobile, salary, profile, joining_date, hr_name):
                      super().__init__(name, address, mobile, salary, profile, joining_date)  # Added hr_name to super
                      self.hr_name = hr_name
                  
                  def hr_details(self):
                      print(self.name)
                      print(self.address)
                      print(self.mobile)
                      print(self.__salary)  # accessing __salary attribute directly from superclass
                      print(self.profile)
                      print(self.joining_date)
                      print(self.hr_name)
              
              # Uncomment the following lines for testing
              # e1 = Employee("Sachin Pawar", "Pune", 7620860053, 20000, "Developer", '31/03/2024')
              # e1.employee_details()
              
              hr1 = HR("Tushar Pawar", "Ahilyanagar", 7620860053, 30000, "Tester", '30/03/2024', "harbinder")
              hr1.hr_details()









                
                class Employee:
                    def __init__(self,name,address,mobile,salary,profile,joining_date):
                        self.name = name
                        self.address = address
                        self.mobile = mobile
                        self.__salary = salary
                        self.profile = profile
                        self.joining_date = joining_date
                    
                    def employee_details(self):
                        print(self.name)
                        print(self.address)
                        print(self.mobile)
                        print(self.__salary)
                        print(self.profile)
                        print(self.joining_date)
                
                class HR(Employee):
                    def __init__(self,name,address,mobile,profile,joining_date,hr_name):
                        super().__init__(name,address,mobile,profile,joining_date)
                        self.hr_name = hr_name
                    
                    def hr_details(self):
                        print(self.name)
                        print(self.address)
                        print(self.mobile)
                        print(self.profile)
                        print(self.joining_date)
                        print(self.hr_name)
                
                
                
                
                # e1 = Employee("Sachin Pawar","Pune",7620860053,20000,"Developer",'31/03/2024')
                # e1.employee_details()
                
                hr1 = HR("Tushar Pawar","Ahilyanagar",7620860053,"Tester",'30/03/2024',"harbinder")
