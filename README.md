# Tarea_interfaz
Apuntes de tarea
import tkinter
import pygame

#-----------------------------Funciones----------------------------------------------------------------------------------

def fibonacci(num):
    if (isinstance (num,int) and (num>=0)):
        return fibonacci_aux(num)
    else:
        return ("el numero debe ser engtero y positivo")
def fibonacci_aux(num):
    if num==0:
        return 0
    elif num==1:
        return 1
    else:
        return fibonacci_aux (num-1) + fibonacci_aux (num-2)
# funcion para para cambiar a la ventana fibonacci
def ir_fibo():
    inicial.forget()
    ventana_fibo.pack(fill='both',expand=1)


#funcion para boton de atras
def atras():
    ventana_fibo.forget()
    ventana_info.forget()
    ventana_ani.forget()
    inicial.pack(fill='both',expand=1)
#funcion para informacion personal
def ir_info():
    inicial.forget()
    ventana_info.pack(fill='both',expand=1)
    
# funcion para animacion

def ir_ani():
    inicial.forget()
    ventana_ani.pack(fill='both',expand=1)
#audio
pygame.mixer.init()
def play_audio():
    pygame.mixer.music.load('audio/Dread Mar I (mp3cut.net).mp3')
    pygame.mixer.music.play(loops=0)


 #--------------------ventanas------------------------------------------------------------------------------------------
    
ventana =  tkinter.Tk() #ventana padre
ventana.geometry("1000x700")
ventana.title("interfaz grafica Brayner Moncada")

foto= tkinter.PhotoImage(file='img/brayner.png')
foto2= tkinter.PhotoImage(file='img/Dread Brayner.png')
foto3= tkinter.PhotoImage(file='img/Pulga.png')

#-------------------------v hijas----------------------------------------------------------------------------------
inicial= tkinter.Frame(ventana)# ventana principal
ventana_fibo = tkinter.Frame(ventana) #ventana fibo
ventana_info = tkinter.Frame(ventana)
ventana_ani = tkinter.Frame(ventana)


 #---------------------Labels----------------------------------------------------------------------------

label_fibo=tkinter.Label(ventana_fibo,text='FUNCION FIBONACCI')# se crea una ventana nueva
label_fibo.pack(pady=20)# corre el texto con base al eje y
label_inicial = tkinter.Label(inicial,text= "Menu Principal")# primer ventana en aparecer
label_inicial.pack(pady=20) # se utiliza para el espacio del texto hacai abajo
label_info = tkinter.Label(ventana_info,text= "INFORMACION DEL PROGRAMADOR")# primer ventana en aparecer de info
label_info.pack(pady=20) # se utiliza pa
label_ani= tkinter.Label(ventana_ani,text= "ANIMACION")# primer ventana en aparecer de info
label_ani.pack(pady=20) # se utiliza pa
label_foto= tkinter.Label(ventana_info,image=foto)
label_foto.place(x=0,y=250)
label_foto2= tkinter.Label(ventana_info,image=foto2)
label_foto2.place(x=300,y=170)
label_foto3= tkinter.Label(ventana_info,image=foto3)
label_foto3.place(x=700,y=200)

label_nombre=tkinter.Label(ventana_info,text='Nombre: Brayner Moncada', font =("Cambria" ,15))
label_nombre.place(x=0 , y = 50)
label_carnet=tkinter.Label(ventana_info,text='Carnet: 2021011317', font =("Cambria" ,15))
label_carnet.place(x=0 , y = 100)
label_genero=tkinter.Label(ventana_info,text='Genero: Masculino', font =("Cambria" ,15))
label_genero.place(x=0, y= 150)
label_edad=tkinter.Label(ventana_info,text='Edad: 18', font =("Cambria" ,15))
label_edad.place(x=0 , y=200)
label_direccion=tkinter.Label(ventana_info,text='Direccion: 1 km noreste salon comunal de Colonia Blanca', font =("Cambria" ,15))
label_direccion.place(x=0, y = 500)
label_grupo=tkinter.Label(ventana_info, text = 'Grupo Preferido: Dread Mar I', font =("Cambria" ,15))
label_grupo.place(x=300 , y = 50)
label_genero=tkinter.Label(ventana_info, text= ' Genero: Reggae', font =("Cambria" ,15))
label_genero.place(x=300 , y=100)
label_deporte=tkinter.Label(ventana_info, text = ' Deporte: Futbol', font =("Cambria" ,15))
label_deporte.place(x=700 , y = 50)
label_fut=tkinter.Label(ventana_info, text = ' Es un deporte que se juega', font =("Cambria" ,15))
label_fut.place(x=700,y=100)
label_fut1=tkinter.Label(ventana_info,text='en equipos de 11 personas', font =("Cambria" ,15))
label_fut1.place(x=700,y=130)
label_fut3=tkinter.Label(ventana_info,text='en el cual gana el que anote mas',font=("Cambria",15))
label_fut3.place(x=700, y = 160)
label_favorita=tkinter.Label(ventana_info,text='Cancion Favorita',font=("Cambria",15))
label_favorita.place(x=300 , y = 385)




#-------------------botones----------------------------------------------------------------------------------------

ir_fibonacci= tkinter.Button(inicial,text= "fibonacci",command= ir_fibo, bg = "Turquoise")
ir_fibonacci.pack(pady=10)
ir_info= tkinter.Button(inicial,text= "informacion personal",command= ir_info, bg = "Turquoise")
ir_info.pack(pady=20)
ir_animacion= tkinter.Button(inicial,text= "animacion",command= ir_ani, bg = "Turquoise")
ir_animacion.pack(pady=30)
volver_fibo= tkinter.Button(ventana_fibo,text="Volver al menu", command= atras, bg="Red")
volver_fibo.place(x=500, y=600)
volver_info= tkinter.Button(ventana_info,text="Volver al menu", command= atras, bg="Red")
volver_info.place(x=500,y=600)
volver_animacion= tkinter.Button(ventana_ani,text="Volver al menu", command= atras, bg="Red")
volver_animacion.place(x=500, y=600)
reproducir= tkinter.Button(ventana_info,text= "play music",command= play_audio, bg = "Yellow")
reproducir.place(x=360, y=430)


inicial.pack()


                       
ventana.mainloop()







