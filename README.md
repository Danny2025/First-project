# First-project
school administration tool
import csv

def write_into_csv(info_list):
    with open("student_info.csv" , 'a', newline='') as csv_file:
        writer = csv.writer(csv_file)

        if csv_file.tell () == 0:
            writer.writerow(["name","Age","Contact_number","Email_id"])
        
        writer.writerow(info_list)

if __name__ =='__main__':
    condition = True
    student_num = 1
    while(condition):
        student_info = input("Enter student information for the student #{} in the following format (Name Age Contact_number Email_id):".format(student_num))
        
        student_info_list = student_info.split(' ')
        

        print("\n Entered info is:\n Name: {}\n Age:{} \n Contact_number:{} \n Email_id:{}"
              .format(student_info_list[0],student_info_list[1],student_info_list[2],student_info_list[3]))

        choise_check = input("is the entered info is correct (yes/no)")

        if choise_check == "yes":
            write_into_csv(student_info_list)

            condition_check = input("Enter (yes/no) if you want to enter information of another student: ")
            if condition_check == "yes":
                 condition = True
                 student_num = student_num + 1
            elif condition_check == "no":
               condition = False       
                
