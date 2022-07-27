algoritmo trabalho_APC;
// Síntese
//  Objetivo:
//  Entrada :
//  Saída   :


principal
	// Declarações

	inteiro sintoma, dores,l,k,z,g,f,v;
	inteiro dia,mes,ano,hora,minuto;
	inteiro valor;
	inteiro j,id;
	texto c,sexo,FIM;
	inteiro i,y,m,a,b,s,q;
	caracter x,x1,x2;
	texto nome,nome_aco;
	texto cpf,cpf_2,outros[8];
	inteiro validar,validar_2;
	FIM="FIM";
	l=0;
	k=0;
	z=0;
	g=0;
	m=0;
	a=0;
	b=0;
	f=0;
	s=0;
	q=0;
	dores=0;

	// Instruções

	///// Apresentação do hospital

	escreval("BEM VINDO AO HOSPITAL FGA.");
	escreval(" ");
	escreval("PARA MELHOR ATENDE-LO VAMOS LHE FAZER ALGUMAS PERGUNTAS.");
	escreval(" ");
	escreval("AGRADEÇO PELA COMPRIENÇÃO, ENTÃO VAMOS COMEÇAR");
	escreval(" ");

	///// Ler nome do paciente: Caso seja uma numero, entao manda rescrever o nome do mesmo

	escreval("NOME DO PACIENTE : ");

	leia(nome);
	faca
		x=caracterTexto(nome,m);
		se(caracterAscii(x)>=48 e caracterAscii(x)<=57)entao
			escreval("DIGITE NOVAMENTE SEU NOME : ");
			leia(nome);
			m=-1;
		fimSe
		m=m+1;
	enquanto(tamanhoTexto(nome)!=m);

	///// Sexo do individuo

	escreval("QUAL É O SEU SEXO :");
	leia(sexo);

	///// Valida CPF

	escreval("DIGITE SEU CPF (PACIENTE) : ")	;
	leia(cpf);
	validar=valida_cpf(cpf);

	se(validar==1)entao
		escreval("CPF VALIDO");
	senao
		faca
			escreval("CPF INVALIDO");
			escreval("DIGITE O CPF NOVAMENTE");
			leia(cpf);
			validar=valida_cpf(cpf);
		enquanto(validar!=1);
	fimSe


	///// Validar idade e o nome do acompanhante

	escreval("DIGITE SUA IDADE : ");
	leia (id);
	se(id<0)entao
		faca
			escreval("DIGITE SUA IDADE NOVAMENTE : ");
			leia (id);
		enquanto(id<0);
	fimSe
	se (id<18)entao
		escreval("MENOR DE IDADE, NECESSITA DE ACOMPANHANTE");
		escreval("DIGITE O NOME DO ACOMPANHANTE : ");
		leia(nome_aco);
		faca
			x1=caracterTexto(nome_aco,a);
			se(caracterAscii(x1)>=48 e caracterAscii(x1)<=57)entao
				escreval("DIGITE NOVAMENTE O NOME : ");
				leia(nome_aco);
				a=-1;
			fimSe
			a=a+1;
		enquanto(tamanhoTexto(nome_aco)!=a);
		escreval("DIGITE SEU CPF (PACIENTE) : ")	;
		leia(cpf_2);
		validar_2=valida_cpf_2(cpf_2);

		se(validar_2==1)entao
			escreval("CPF VALIDO");
		senao
			faca
				escreval("CPF INVALIDO");
				escreval("DIGITE O CPF NOVAMENTE");
				leia(cpf_2);
				validar_2=valida_cpf_2(cpf_2);
			enquanto(validar_2!=1);
		fimSe

	senao
		se(id>=70)entao
			escreval("IDOSO, NECESSITA DE ACOMPANHANTE");
			escreval("DIGITE O NOME DO ACOMPANHANTE : ");
			leia(nome_aco);
			faca
				x2=caracterTexto(nome_aco,b);
				se(caracterAscii(x2)>=48 e caracterAscii(x2)<=57)entao
					escreval("DIGITE NOVAMENTE O NOME : ");
					leia(nome_aco);
					b=-1;
				fimSe
				b=b+1;
			enquanto(tamanhoTexto(nome_aco)!=b);
			escreval("DIGITE SEU CPF DO ACOMPANHANTE : ")	;
			leia(cpf_2);
			validar=valida_cpf_2(cpf_2);

			se(validar_2==1)entao
				escreval("CPF VALIDO");
			senao
				faca
					escreval("CPF INVALIDO");
					escreval("DIGITE O CPF NOVAMENTE");
					leia(cpf_2);
					validar_2=valida_cpf_2(cpf_2);
				enquanto(validar_2!=1);
			fimSe

		senao
			escreval("ADULTO: CONTINUE SEU CADASTRO");
			escreval("SEM ACOMPANHANTE");
		fimSe
	fimSe

	///// Valida a data de entrada do paciente

	escreval("DIGITE O DIA DE ENTRADA : ");
	leia(dia);
	escreval("DIGITE O MÊS DE ENTRADA : ");
	leia(mes);
	escreval("DIGITE O ANO DE ENTRADA: ");
	leia(ano);
	escreval("DIGITE A HORA DE ENTRADA : ");
	leia(hora);
	escreval("DIGITE O MINUTO DE ENTRADA : ");
	leia(minuto);

	valor=valida_data(dia,mes,ano,hora,minuto);

	se (valor!=5)entao
		faca
			escreval("DATA OU HORA INCORRETA. DIGITE NOVAMENTE :");
			escreval("DIGITE O DIA DE ENTRADA NOVAMENTE : ");
			leia(dia);
			escreval("DIGITE O MÊS DE ENTRADA NOVAMENTE : ");
			leia(mes);
			escreval("DIGITE O ANO DE ENTRADA NOVAMENTE : ");
			leia(ano);
			escreval("DIGITE A HORA DE ENTRADA NOVAMENTE : ");
			leia(hora);
			escreval("DIGITE O MINUTO DE ENTRADA NOVAMENTE : ");
			leia(minuto);

			valor=valida_data(dia,mes,ano,hora,minuto);

		enquanto(valor!=5);

	fimSe

	///// SINTOMAS DOS PACIENTES

	escreval("Sintoma_1 = DOR DE CABEÇA");
	escreval("Sintoma_2 = MEMBROS QUEBRADOS");
	escreval("Sintoma_3 = TORMENCIA EM UM DOS LADOS");
	escreval("Sintoma_4 = FALA ARRASTADA");
	escreval("Sintoma_5 = HEMORRAGIA");
	escreval("Sintoma_6 = DOR NO CORPO");
	escreval("Sintoma_7= FADIGA");
	escreval("Sintoma_8 = DOR NO PEITO");
	escreval("Sintoma_9 = BRAÇO FORMIGANDO");
	escreval("Sintoma_10 = FEBRE");
	escreval("Sintoma_11 = ENJOO");
	escreval("Sintoma_12 = DOR NO ESTOMAGO");
	escreval("Sintoma_13 = AZIA");
	escreval("Observação - Digite o numero. Ao fim digite 0.");

	escreval("DIGITE SEU SINTOMAS");

	faca
		leia(sintoma);
		se(sintoma==1 ou sintoma==5 ou sintoma==6 ou sintoma==7 ou sintoma==10 ou sintoma==11)entao
			l=l+1;
		senao
			se(sintoma==2)entao
				k=k+1;
			senao
				se(sintoma==3 ou sintoma==4)entao
					z=z+1;
				senao
					se(sintoma==8 ou sintoma==9)entao
						g=g+1;
					senao
						se(sintoma==12 ou sintoma==13)entao
							f=f+1;
						fimSe
					fimSe
				fimSe
			fimSe
		fimSe
		dores=dores+sintomas(sintoma);
	enquanto(sintoma!=0);

	escreval("CASO HAJA OUTROS SINTOMAS DIGITE AQUI : ");
	escreval("AO FIM DIGITE (FIM)");
	escreval("CASO NÃO HAJA OUTRO SINTOMA, DIGITE NAO E FIM.");

	faca
		leia (outros[s]);
		se(comparaTexto(outros[s],FIM)==0)entao
			s=s-s;
			s=-1;
		fimSe
		s=s+1;
	enquanto(s!=0);


	escreval(" ");

	escreval("NOME DO PACIENTE : ",nome);
	escreval("SEXO DO PACIENTE : ",sexo);
	escreval("CPF DO PACIENTE : ",cpf);
	escreval("IDADE DO PACINETE : ", id);
	se(id<18 ou id>70)entao
		escreval("NOME DO ACOMPANHANTE : ",nome_aco);
		escreval("CPF DO ACOMPANHANTE : ",cpf_2);
	senao
		escreval("SEM ACOMAPANHANTE");
	fimSe

	escreval("DATA DE ENTRADA :  ", dia, " / ",mes," / ",ano);
	escreval("HORARIO DE ENTRADA : ", hora ,":",minuto);

	escreval("OUTROS SINTOMAS : ");
	escreval(" ");

	faca
		se(comparaTexto(outros[q],FIM)!=0)entao
			escreval(outros[q]);
		senao
			q=-1;
		fimSe
		q=q+1;
	enquanto(q!=0);

	escreval(" ");

	se (dores<=2)entao
		escreval("PULSEIRA VERDE");
	senao
		se(dores>2 e dores<=4)entao
			escreval("PULSEIRA AMARELA");
		senao
			se(dores>4 e dores<=7)entao
				escreval("PULSEIRA VERMELHA");
			senao
				escreval("EMERGÊNCIA");
			fimSe
		fimSe
	fimSe

	se(l>=1)entao
		escreval("DIRIJA-SE À CLÍNICA MÉDICA");
	senao
		se(k>=1)entao
			escreval("DIRIJA-SE À ORTOPEDIA");
		senao
			se(z>=1)entao
				escreval("DIRIJA-SE À NEUROLOGIA");
			senao
				se(g>=1)entao
					escreval("DIRIJA-SE À CARDIOLOGIA");
				senao
					se(f>=1)entao
						escreval("DIRIJA-SE À GASTROENTEROLOGIA");
					fimSe
				fimSe
			fimSe
		fimSe
	fimSe


	escreval(" ");


fimPrincipal

funcao inteiro sintomas (inteiro sintoma)

	inteiro j;
	j=0;
	se(sintoma==1)entao
		j=j+1;
	fimSe
	se(sintoma==2)entao
		j=j+2;
	fimSe
	se(sintoma==3)entao
		j=j+4;
	fimSe
	se(sintoma==4)entao
		j=j+4;
	fimSe
	se(sintoma==5)entao
		j=j+3;
	fimSe
	se(sintoma==6)entao
		j=j+2;
	fimSe
	se(sintoma==7)entao
		j=j+1;
	fimSe
	se(sintoma==8)entao
		j=j+3;
	fimSe
	se(sintoma==9)entao
		j=j+3;
	fimSe
	se(sintoma==10)entao
		j=j+1;
	fimSe
	se(sintoma==11)entao
		j=j+1;
	fimSe
	se(sintoma==12)entao
		j=j+2;
	fimSe
	se(sintoma==13)entao
		j=j+1;
	fimSe

	retorna j;

fimFuncao
funcao inteiro valida_data(inteiro dia, inteiro mes, inteiro ano, inteiro hora, inteiro minuto)

	inteiro i,soma;
	soma=0;

	para (i de 1 ate 1 passo 1)faca
		se(mes>0 e mes<13)entao
			soma=soma+1;
			se(ano>=00)entao
				se (ano%4==0)entao
					soma=soma+1;
					escolha (mes)
					caso 01
						se(dia>0 e dia<32)entao
							soma=soma+1;
						fimSe
						interrompa;
					caso 02
						se(dia>0 e dia<30)entao
							soma=soma+1;
						fimSe
						interrompa;
					caso 03
						se(dia>0 e dia<32)entao
							soma=soma+1;
						fimSe
						interrompa;
					caso 04
						se(dia>0 e dia<31)entao
							soma=soma+1;
						fimSe
						interrompa;
					caso 05
						se(dia>0 e dia<32)entao
							soma=soma+1;
						fimSe
						interrompa;
					caso 06
						se(dia>0 e dia<31)entao
							soma=soma+1;
						fimSe
						interrompa;
					caso 07
						se(dia>0 e dia<32)entao
							soma=soma+1;
						fimSe
						interrompa;
					caso 8
						se(dia>0 e dia<32)entao
							soma=soma+1;
						fimSe
						interrompa;
					caso 9
						se(dia>0 e dia<31)entao
							soma=soma+1;
						fimSe
						interrompa;
					caso 10
						se(dia>0 e dia<32)entao
							soma=soma+1;
						fimSe
						interrompa;
					caso 11
						se(dia>0 e dia<31)entao
							soma=soma+1;
						fimSe
						interrompa;
					caso 12
						se(dia>0 e dia<32)entao
							soma=soma+1;
						fimSe
						interrompa;
					fimEscolha
				senao
					se(ano%4!=0)entao
						soma=soma+1;
						escolha (mes)
						caso 01
							se(dia>0 e dia<32)entao
								soma=soma+1;
							fimSe
							interrompa;
						caso 02
							se(dia>0 e dia<29)entao
								soma=soma+1;
							fimSe
							interrompa;
						caso 03
							se(dia>0 e dia<32)entao
								soma=soma+1;
							fimSe
							interrompa;
						caso 04
							se(dia>0 e dia<31)entao
								soma=soma+1;
							fimSe
							interrompa;
						caso 05
							se(dia>0 e dia<32)entao
								soma=soma+1;
							fimSe
							interrompa;
						caso 06
							se(dia>0 e dia<31)entao
								soma=soma+1;
							fimSe
							interrompa;
						caso 07
							se(dia>0 e dia<32)entao
								soma=soma+1;
							fimSe
							interrompa;
						caso 8
							se(dia>0 e dia<32)entao
								soma=soma+1;
							fimSe
							interrompa;
						caso 9
							se(dia>0 e dia<31)entao
								soma=soma+1;
							fimSe
							interrompa;
						caso 10
							se(dia>0 e dia<32)entao
								soma=soma+1;
							fimSe
							interrompa;
						caso 11
							se(dia>0 e dia<31)entao
								soma=soma+1;
							fimSe
							interrompa;
						caso 12
							se(dia>0 e dia<32)entao
								soma=soma+1;
							fimSe
							interrompa;
						fimEscolha

					fimSe
				fimSe
				se(hora>-1 e hora<24)entao
					soma=soma+1;
				fimSe
				se(minuto>-1 e minuto<60)entao
					soma=soma+1;
				fimSe
			fimSe
		fimSe
	fimPara
	retorna soma;
fimFuncao

funcao inteiro valida_cpf (texto cpf)

	inteiro r,t,c,h,i,d;
	inteiro soma_1,soma_2;
	inteiro resto_1,resto_2;
	caracter x;
	inteiro p,v;
	r=10;
	c=0;
	t=11;
	h=0;
	soma_1=0;
	soma_2=0;
	d=0;
	v=1;
	p=1;

	enquanto(c!=9)faca
		x=caracterTexto(cpf,c);
		soma_1=soma_1+((r)*x);
		c=c+1;
		r=r-1;
	fimEnquanto

	enquanto(c!=11)faca
		x=caracterTexto(cpf,c);
		c=c+1;
		se(c==10)entao
			v=v*x;
		fimSe
	fimEnquanto

	enquanto(h!=10)	faca
		x=caracterTexto(cpf,h);
		soma_2=soma_2+((t)*x);
		h=h+1;
		t=t-1;
	fimEnquanto

	enquanto(h!=11)	faca
		x=caracterTexto(cpf,h);
		h=h+1;
		se(h==11)entao
			p=p*x;
		fimSe
	fimEnquanto

	resto_1=soma_1*10%11;
	resto_2=soma_2*10%11;

	se (soma_1==10 e soma_2==10)entao
		resto_1=0;
		resto_2=0;
	senao
		se(soma_1==10)entao
			resto_1=0;
		senao
			se(soma_2==10)entao
				resto_2=0;
			fimSe
		fimSe
	fimSe

	se (v==resto_1 e p==resto_2)entao
		d=d+1;
	fimSe

	retorna d;

fimFuncao
funcao inteiro valida_cpf_2 (texto cpf_2)

	inteiro r,t,c,h,i,u;
	inteiro soma_1,soma_2;
	inteiro resto_1,resto_2;
	caracter x;
	inteiro p,v;
	r=10;
	c=0;
	t=11;
	h=0;
	soma_1=0;
	soma_2=0;
	u=0;
	v=1;
	p=1;

	enquanto(c!=9)faca
		x=caracterTexto(cpf_2,c);
		soma_1=soma_1+((r)*x);
		c=c+1;
		r=r-1;
	fimEnquanto

	enquanto(c!=11)faca
		x=caracterTexto(cpf_2,c);
		c=c+1;
		se(c==10)entao
			v=v*x;
		fimSe
	fimEnquanto

	enquanto(h!=10)	faca
		x=caracterTexto(cpf_2,h);
		soma_2=soma_2+((t)*x);
		h=h+1;
		t=t-1;
	fimEnquanto

	enquanto(h!=11)	faca
		x=caracterTexto(cpf_2,h);
		h=h+1;
		se(h==11)entao
			p=p*x;
		fimSe
	fimEnquanto

	resto_1=soma_1*10%11;
	resto_2=soma_2*10%11;

	se (soma_1==10 e soma_2==10)entao
		resto_1=0;
		resto_2=0;
	senao
		se(soma_1==10)entao
			resto_1=0;
		senao
			se(soma_2==10)entao
				resto_2=0;
			fimSe
		fimSe
	fimSe

	se (v==resto_1 e p==resto_2)entao
		u=u+1;
	fimSe

	retorna u;

fimFuncao
