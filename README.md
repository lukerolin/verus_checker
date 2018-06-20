# verus_checker
# A program to help users quickly identify resupply patients

import openpyxl, os, shutil
from openpyxl import Workbook
tfile = (r"G:\My Drive\Programs\all_id.xlsx")
sfile = (r"C:\Users\lpetty\pprograms")
shutil.copy(tfile, sfile)
wb = openpyxl.load_workbook('all_id.xlsx')
sheet = wb.active

source = []
for row in range(2, sheet.max_row + 1):
	btid = sheet['A' + str(row)].value
	
	source.append(str(btid))
	
def verus_find():
	uin = input(str("Enter the Brightree ID #: "))
	
	
	if uin == '1':
		os.remove(r"C:\Users\lpetty\pprograms\all_id.xlsx")
		quit()
	else:
		if uin in source:
				print('\n'"V E R U S"'\n')
				verus_find()
		else:
			print('\n'"M E D I G Y"'\n')
			verus_find()
			
verus_find()
