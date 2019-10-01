# Estudo das aulas - Sistemas Operacionais
Este repositório serve para exercitar C++ e conceitos de Sistemas Operacionais que aprendi na Faculdade.

## Exercício 1 

Criar o subdiretório **cabecalhos** para conter os arquivos abaixo

Arquivo cabeçalho
```cpp
#include <iostream>
using namespace std;

class Hello 
{
public:
   void sayHello();
};
```

Arquivo de definção de classe `classe1.cpp`
```cpp
#include hello.h

void Hello::sayHello() 
{
    cout << "Maven - Testando C++ ..." << endl;
}
```

Sair do subdiretório **cabecalhos**  e criar o arquivo principal.cpp no diretório acima.

Arquivo Principal principal.cpp

```cpp
#include "cabecalhos/classe1.h"

int main( ) 
{
    Hello objeto;
    objeto.sayHello();
    return 0;
}
```

Compilar tudo usando um programa de Make (pode ser NMake do windows, CMake (multiplataforma) ou Make do linux)

Neste exemplo, usamos o make do linux para criar o Makefile abaixo:
```Makefile
CABECALHOS := cabecalhos

all: principal.o classe1.o
	g++ -I$(CABECALHOS) -o oi.bin principal.o classe1.o

principal.o: principal.cpp
	g++ -I$(CABECALHOS) -c principal.cpp

classe1.o: classe1.cpp
	g++ -I$(CABECALHOS) -c classe1.cpp

clean:
	rm -rf ./oi.bin *.o

```

Para executar a compilação, digite "make all" no prompt do linux

