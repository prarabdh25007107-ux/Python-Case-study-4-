# Python-Case-study-4-
# Open file
file = open("logfile.txt", "r")
# ---------- Task 1: Basic File Reading ----------
# read()
content = file.read()
print("Full Content:\n", content)
# Total lines
lines = content.split("\n")
print("Total number of lines:", len(lines))
# First 2 lines
print("\nFirst 2 lines:")
print("\n".join(lines[:2]))
# Last 2 lines
print("\nLast 2 lines:")
print("\n".join(lines[-2:]))
file.close()
# readline() and readlines()
file = open("logfile.txt", "r")
print("\nUsing readline():")
print(file.readline())
print(file.readline())
file.seek(0)
print("\nUsing readlines():")
all_lines = file.readlines()
print(all_lines)
file.close()
# ---------- Task 2: Log Classification ----------
file = open("logfile.txt", "r")
lines = file.readlines()
count_dict = {"INFO": 0, "WARNING": 0, "ERROR": 0}
for line in lines:
if "INFO" in line:
count_dict["INFO"] += 1
if "WARNING" in line:
count_dict["WARNING"] += 1
if "ERROR" in line:
count_dict["ERROR"] += 1
print("\nLog Count:", count_dict)
file.close()
# ---------- Task 3: Write Filtered Files ----------
info_file = open("info_logs.txt", "w")
warning_file = open("warning_logs.txt", "w")
error_file = open("error_logs.txt", "w")
for line in lines:
if "INFO" in line:
info_file.write(line)
if "WARNING" in line:
warning_file.write(line)
if "ERROR" in line:
error_file.write(line)
info_file.close()
warning_file.close()
error_file.close()
# ---------- Task 4: Search Feature ----------
keyword = input("\nEnter keyword to search: ")
file = open("logfile.txt", "r")
lines = file.readlines()
result = []
print("\nMatching lines:")
for line in lines:
if keyword in line:
print(line.strip())
result.append(line)
file.close()
# Save results
res_file = open("search_result.txt", "w")
res_file.writelines(result)
resfile.close()
# ---------- File Pointer (seek) Operations ----------
file = open("logfile.txt", "r")
# Read first 50 characters
print("\nFirst 50 characters:")
print(file.read(50))
# Move to beginning
file.seek(0)
print("\nAfter seek(0):")
print(file.read(50))
# Move to middle
file.seek(len(content)//2)
print("\nFrom middle:")
print(file.read(50))
# Move to last 100 characters
file.seek(-100, 2)
print("\nLast 100 characters:")
file.close()
