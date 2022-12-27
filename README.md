
from time import sleep
from tkinter import*

def somar():
	atual=texto.get()
	global primeironumero
	global operacao
	operacao='soma'
	primeironumero=int(atual)
	texto.delete(0,END)
	return
def subtracao():
	atual=texto.get()
	global primeironumero
	global operacao
	operacao='subtracao'
	primeironumero=int(atual)
	texto.delete(0,END)
	return
def multiplicacao():
	atual=texto.get()
	global primeironumero
	global operacao
	operacao='multiplicacao'
	primeironumero=int(atual)
	texto.delete(0,END)
	return
def divisao():
	atual=texto.get()
	global primeironumero
	global operacao
	operacao='divisao'
	primeironumero=int(atual)
	texto.delete(0,END)
	return
def igual():
	atual=texto.get()
	texto.delete(0, END)
	
	if operacao=='soma':
		texto.insert(0, primeironumero + int(atual))
	elif operacao=='subtracao':
		texto.insert(0, primeironumero - int(atual))
	elif operacao=='divisao':
		texto.insert(0, primeironumero / int(atual))
	else:
		texto.insert(0, primeironumero * int(atual))
	return
def deletar():
	texto.delete(0, END)
def clique(clicado):
	atual=texto.get()
	texto.delete(0, END)
	texto.insert(0, str(atual)+ str(clicado))

#programa principal
janela = Tk()

janela.title('Calculadora 2021')
janela.geometry('300x500')
janela.resizable(0,0)
janela.configure(background= 'dark grey')

texto1= Label (text='Calculadora 2021'.capitalize(), background='dark grey', font ='arial, 9')
texto1.place(x=2, y=7)

texto2= Label(text='''Developed by:\n           Technological world''', background='dark grey', font='arial, 9')
texto2.place(x=0, y=455)

texto = Entry(janela, font = ('arial', 14), bd=10, relief=RIDGE, width=25, justify='left')
texto.place(x=2, y=30)

botao1 = Button(text='1', width=5, bd=4, relief= RIDGE, height=3,
                background='light gray', command=lambda:clique('1')).place(x=55 ,y=75)

botao2 = Button(text='2', width=5, bd=4, relief= RIDGE, height=3,
                background='light gray',command=lambda:clique('2')).place(x=110, y=75)

botao3 = Button(text='3', width=5, bd=4, relief=RIDGE, height=3,
                backgroun='light gray', command=lambda:clique('3')).place(x=165, y=75)

botao4 = Button(text='4', width=9, bd=4, relief=RIDGE, height=3,
                background='light gray', command=lambda:clique('4')).place(x=220, y=75)

botao5 = Button(text='5', width=5, bd=4, relief=RIDGE, height=3,
                background='light gray',command=lambda:clique('5')).place(x=2, y=140)

botao6 = Button(text='6', width=5, bd=4, relief=RIDGE, height=3,
                background='light gray',command=lambda:clique('6')).place(x=55, y=140)

botao7 = Button(text='7', width=5, bd=4, relief=RIDGE, height=3,
                background='light gray',command=lambda:clique('7')).place(x=110, y=140)

botao8 = Button(text='8', width=5, bd=4, relief=RIDGE, height=3,
                background='light gray',command=lambda:clique('8')).place(x=165, y=140)

botao9 = Button(text='9', width=9, bd=4, relief=RIDGE, height=3,
                background='light gray',command=lambda:clique('9')).place(x=220, y=140)

botao0 = Button(text=' 0 ', width=5, bd=4, relief=RIDGE, height=3,
                background='light gray',command=lambda:clique('0')).place(x=2, y=75)

botao10 = Button(text=' + ', width=5, bd=4, relief=RIDGE, height=3,
                 background='light gray',command=somar).place(x=2, y=205)

botao11 = Button(text='- ', width=5, bd=4, relief=RIDGE, height=3,
                 background='light gray',command=subtracao).place(x=55, y=205)

botao13 =Button(text='×', width=5, bd=4,relief=RIDGE, height=3,
                background='light gray',command=multiplicacao).place(x=110, y=205)

botao14 = Button(text='=', width=40, bd=4, relief=RIDGE, height=3,
                 background='light gray',command=igual).place(x=2, y=270)

botao15 = Button(text='zerar', width=40, bd=4,relief= RIDGE, height=3,
                 background='light gray',command= deletar).place(x=2, y=335)

botao16 = Button(text='÷', width=5, bd=4, relief=RIDGE, height=3,
                 background='light gray', command=divisao).place(x=165, y=205)

botao17 = Button(text='.', width=9, bd=4, relief=RIDGE, height=3,
                 background='light gray',command=lambda:clique('.')).place(x=220, y=205)

janela.mainloop()
