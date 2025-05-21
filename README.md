# Windows-basic-commands-batchscript
Ex08-Windows-basic-commands-batchscript

# AIM:
To execute Windows basic commands and batch scripting

# DESIGN STEPS:

### Step 1:

Navigate to any Windows environment installed on the system or installed inside a virtual environment like virtual box/vmware 

### Step 2:

Write the Windows commands / batch file . Save each script in a file with a .bat extension. Ensure you have the necessary permissions to perform the operations. Adapt paths as needed based on your system configuration.
### Step 3:

Execute the necessary commands/batch file for the desired output. 




# WINDOWS COMMANDS:
## Exercise 1: Basic Directory and File Operations
Create a directory named "my-folder"

## COMMAND AND OUTPUT
### mkdir my-folder
![image](https://github.com/user-attachments/assets/f2c3927d-f94d-44a9-8282-57fad9226a62)

Remove the directory "my-folder"

## COMMAND AND OUTPUT
### rmdir my-folder
![image](https://github.com/user-attachments/assets/8a4c106a-267d-45f5-a84a-84b840516891)

Create the file Rose.txt

## COMMAND AND OUTPUT
### COPY CON Rose.txt
![image](https://github.com/user-attachments/assets/7534c5a4-4053-4f8e-a3e2-bc7ba7f30317)


Create the file hello.txt using echo and redirection

## COMMAND AND OUTPUT
### echo “hello world” > hello.txt
![image](https://github.com/user-attachments/assets/7c80c657-5866-43b7-9cdb-0be8cf9daea5)

Copy the file hello.txt into the file hello1.txt

## COMMAND AND OUTPUT
### copy hello.txt hello1.txt
![image](https://github.com/user-attachments/assets/834018cd-d372-4973-82dd-b516a844a8da)

Remove the file hello1.txt

## COMMAND AND OUTPUT
### del hello1.txt
![image](https://github.com/user-attachments/assets/e08591fa-4af0-466d-bd7b-f9905c3ff259)

List out the file hello1.txt in the current directory

## COMMAND AND OUTPUT
### dir hello1.txt
![image](https://github.com/user-attachments/assets/556cf8b0-52a5-45c3-9a8e-959999290003)

List out all the associated file extensions 

## COMMAND AND OUTPUT
### assoc | more
![image](https://github.com/user-attachments/assets/b9205e1d-2129-4d7a-9923-975db503b115)

Compare the file hello.txt and rose.txt

## COMMAND AND OUTPUT
### fc Hello.txt Rose.txt
![image](https://github.com/user-attachments/assets/823417ac-2765-46da-a20e-7f26dce947bb)

## Exercise 2: Advanced Batch Scripting
Create a batch file named on the desktop. The batch file need to have a variable assigned with a desired name for ex. name="John" and display as "Hello, John".
```
@echo off
set name=John
echo Hello, %name%!
pause

```
## OUTPUT
![image](https://github.com/user-attachments/assets/5c95478a-04f5-43a1-8691-59d80002afbf)



Create a batch file  on the desktop that checks whether a user-input number is odd or not. The script should:
Prompt the user to enter a number.
Calculate the remainder when the number is divided by 2.
Display whether the number is odd or not.
Ask the user if they want to check another number.
Repeat the process if the user enters Y, and exit with a thank-you message if the user enters N.
Handle invalid inputs for the continuation prompt (Y/N) gracefully.
```
@echo off
:main
set /p number=Enter a number: 
rem Calculate remainder when divided by 2
set /a remainder=%number% %% 2
if %remainder%==1 (
    echo %number% is an odd number.
) else (
    echo %number% is not an odd number.
)
:choice
set /p continue=Do you want to check another number? (Y/N): 
if /i "%continue%"=="Y" goto main
if /i "%continue%"=="N" goto end
echo Invalid choice, please enter Y or N.
goto choice
:end
echo Thank you for using the odd number checker!
pause
```
## OUTPUT
![image](https://github.com/user-attachments/assets/a1f1a01c-bba9-4ad1-b5eb-26887f8146b3)

Write a batch file that uses a FOR loop to iterate over a sequence of numbers (1 to 5) and displays each number with the label Number:. The output should pause at the end.
```
@echo off
for %%i in (1 2 3 4 5) do (
    echo Number: %%i
)
pause
```
## OUTPUT
![image](https://github.com/user-attachments/assets/790e306b-8178-464e-83fd-f28c8eef12ad)

Write a batch script to check whether a file named sample.txt exists in the current directory. If the file exists, display the message sample.txt exists. Otherwise, display sample.txt does not exist. Pause the script at the end to view the result.

Instructions:
Use the IF EXIST conditional statement.
Make sure the script works for files located in the same directory as the batch file.
Use pause to keep the command window open after displaying the message.
Expected Output (if the file exists):
```
@echo off
if exist sample.txt (
    echo sample.txt exists.
) else (
    echo sample.txt does not exist.
)
pause

```
## OUTPUT
![image](https://github.com/user-attachments/assets/f3959234-31f2-4eb3-82d9-50c41eb0d05d)

Write a batch script that displays a simple menu with three options:
Say Hello – Displays the message Hello, World!
Create a File – Creates a file named newfile.txt with the content This is a new file
Exit – Exits the script with a goodbye message
The script should repeatedly display the menu until the user chooses to exit. Use goto statements to handle menu navigation.
```
@echo off
:menu
echo 1. Say Hello
echo 2. Create a File
echo 3. Exit
set /p choice=Choose an option: 
if "%choice%"=="1" goto hello
if "%choice%"=="2" goto createfile
if "%choice%"=="3" goto end

:hello
echo Hello, World!
goto menu

:createfile
echo Creating a file...
echo This is a new file > newfile.txt
goto menu
:end
echo Goodbye!
pause

```
## OUTPUT
![image](https://github.com/user-attachments/assets/a11cd09f-8035-402e-be68-d5b4966e5435)

# RESULT:
The commands/batch files are executed successfully.

