# test
def char(file_name):
	f = open(file_name, 'r') 
	return len(f.read())	    #字符数

def toline(file_name):
	f = open(file_name,"r")
	read=f.readlines()
	return len(read)            #行数

def words(file_name):
	f = open(file_name,'r')
	read=re.split(r'[a-zA-Z]+',f.read())
	return len(read)            #词数
		
###扩展部分
def expend(file_name):
	f = open(file_name,'r')
	fline = 0
	lined = 0     # 行数
	empty_line = 0 # 空行数
	code_line = 0  # 代码行
	comment_line = 0# 注释行
	is_comment = False #行注释标记
	comment_sign = 0
	read = f.read().split(r'\n')
	
	for line in read:
        fline += 1
        line= line.strip()
        if not is_comment:
            if len(line)<=1:
                empty_line += 1
            elif line.startswith('#'): #检索以'#'开头的单行注释
                comment_line += 1
            elif line.startswith("'''") or line.startswith('"""'):
                 comment_sign += 1
                 lined=fline
                 is_comment =True
                 if  comment_sign%2==0 and comment_sign>0:
                     comment_line = comment_line + fline - lined
                     is_comment = False
                     lined = fline
            else: code_line += 1
		        code_line += 1	
	print('空行数：'，empty_line)	
	print('代码行：'，code_line)	
	print('标识行：'，comment_line)	
	
	
def main()
   str.name = input('请输入命令及地址：\n').split()
   if   str == '-c':
	   print ('字符数:',getchar(name))
   elif str == '-w':
	   print ('单词数:',getwords(name))
   elif str == '-1':
	   print ('行数:',getline(name))	
   elif str == '-a':
	   getexpend(name)
   
   	
	    
		
		
		
	
