# openssl-1.1.1_u1604

- Fonte: [https://www.openssl.org/source/old/1.1.1/](https://www.openssl.org/source/old/1.1.1/)

## Instalando dependências
>checkinstall = OPCIONAL
```bash
sudo apt install make gcc+ libc6-dev checkinstall
```
## Baixando e extraindo o pacote

```bash
cd /usr/src/
wget  --no-check-certificate https://www.openssl.org/source/old/1.1.1/openssl-1.1.1w.tar.gz
tar -xzvf openssl-1.1.1w.tar.gz 
cd openssl-1.1.1w/
```
## Compilando

```bash
./config
make
```
## Instalando

Há 2 formas de instalar, direto pelo source compilado e via checkinstall
Via checkinstall, é criado um pacote e então dá pra instalar usando dpkg.

- **Instalando via source**

```bash
sudo make install
```
- **Instalando via checkinstall**

Usando a opção "-y" é criado e instalado o pacote automaticamente.  

```bash
checkinstall -y
```
- **verificando se está instalado (checkinstall):**
```bash
cd
dpkg -l openssl
```
## Verificando a versão do comando  

```bash
openssl version -a
```

Se der esta mensagem de erro:

>bash: /usr/bin/openssl: No such file or directory

Faça um novo link:

```bash
ln -sf /usr/local/bin/openssl /usr/bin/openssl
ln -sf /usr/local/bin/c_rehash /usr/bin/c_rehash
```
Atualize as informações de bibliotecas no sistema:

```bash
ldconfig
```
