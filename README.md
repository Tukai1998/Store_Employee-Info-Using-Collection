# Store_Employee-Info-Using-Collection

import java.util.*;
public class MainEmp {                           //CHILD CLASS
public static void main(String[] args) {
	Scanner sc=new Scanner(System.in);
	ArrayList<Employee> emps=new ArrayList<Employee>();
	do {
        System.out.println("enter the id name & salary: ");
        int id=sc.nextInt();
        String name=sc.next();
        double sal=sc.nextDouble();
        Employee emp=new Employee(id,name,sal);
        emps.add(emp);
        System.out.println("Do you have more Employees Details: ");
        String res=sc.next();
        if(res.equalsIgnoreCase("no"));
         break;
	}while(true);
	System.out.println("Employee Information: ");
	for(Employee e:emps) {
		System.out.println(e);
	}
//<----------------------------------------------------------------->
	Employee hemp=getHighestSal(emps);                                      // Print Highest Salary in Employee Info
	System.out.println("Highest salary employee info: ");
	System.out.println(hemp);
//<------------------------------------------------------------------>
	List<Employee> es=getEmployees(emps,40000.00);                         //Print Employee Info whose salary more than 40000
	System.out.println("employee info whose salary more than 40000: ");
	for(Employee emp:es) {
		System.out.println(emp);
	}
	
}
static List<Employee> getEmployees(ArrayList<Employee> emps, double sl) {
	List<Employee> ls=new ArrayList<Employee>();
	for(Employee em:emps) {
		if(em.sal>=sl)
			ls.add(em);
	}
	return ls;
}

static Employee getHighestSal(ArrayList<Employee> emps) {
	Employee hs=emps.get(0);
	for(int i=1;i<emps.size();i++) {
		if(emps.get(i).sal>hs.sal)
			hs=emps.get(i);
	}
	return hs;
}


}
=========================================================================================================================================================
=========================================================================================================================================================
public class Employee {                           //MAIN CLASS
int id;
String name;
double sal;
Employee(int id,String name,double sal){
	
	this.id=id;
	this.name=name;
	this.sal=sal;
}

@Override
public String toString() {
	return "Employee ["+id+","+name+","+sal+"]";
}
}
