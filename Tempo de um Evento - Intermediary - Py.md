código feito com base nessa questão:
=====

Pedrinho está organizando um evento em sua Universidade. O evento deverá ser no mês de Abril, iniciando e terminando dentro do mês.

O problema é que Pedrinho quer calcular o tempo que o evento vai durar, uma vez que ele sabe quando inicia e quando termina o evento.

Sabendo que o evento pode durar de poucos segundos a vários dias, você deverá ajudar Pedrinho a calcular a duração deste evento.

*linguagem utilizada: Python*

Resolution:
=====

    dia,dat1=input().split()
    dat1 = int(dat1)
    h1,m1,s1=map(int,input().split(":"))

    dia,dat2=input().split()
    dat2 = int(dat2)
    h2,m2,s2=map(int,input().split(":"))

    s = s2 - s1
    m = m2 - m1
    h = h2 - h1
    d = dat2 - dat1

    if(s<0):
        s+=60
        m-=1
    if(m<0):
        m+=60
        h-=1
    if(h<0):
        h+=24
        d-=1
    print(f"{d} dia(s)")
    print(f"{h} hora(s)")
    print(f"{m} minuto(s)")
    print(f"{s} segundo(s)")