# Guia de Instalação do Switch Aruba 6100

## Conectar ao Switch via Porta Serial

### 1. Instalar o GNU Screen em uma Distribuição Linux

Para instalar o GNU Screen, use o gerenciador de pacotes da sua distribuição. Por exemplo, no Ubuntu:

```bash
sudo apt-get install screen
```

### 2. Localizar a Porta Serial

Para localizar a porta serial à qual o switch está conectado, use o comando `dmesg`:

```bash
dmesg | grep tty
```

### 3. Conectar ao Switch

Conecte-se ao switch utilizando o comando `screen`:

```bash
screen /dev/ttyS0 9600
```

Substitua `/dev/ttyS0` pela porta correta localizada no passo anterior e `9600` pela velocidade de comunicação adequada, se necessário.

---

## Configuração do Switch Aruba 6100

### 1. Configurar o Hostname e o IP

Entre no modo de configuração e ajuste o hostname e o IP do switch:

```bash
conf

hostname SW-ARUBA-6100-X
interface vlan 1
ip address 172.21.39.6X/22
no ip dhcp
```

Substitua `X` no endereço IP pelo valor apropriado para o seu ambiente de rede.

### 2. Configurar o Servidor SNMP

Configure o servidor SNMP com as informações da sua equipe e localidade:

```bash
snmp-server vrf default
snmp-server community secel
snmp-server system-contact Equipe de Redes - SECEL-MT
snmp-server system-location Datacenter - SECEL-MT
snmp-server system-description Switch Aruba 6100 48p
ip route 0.0.0.0/0 192.10.10.10
```

### 3. Configure a Senha

Altere a senha padrão do usuário.

```
config
user admin plaintext
```

### 4. Salvar a Configuração

Salve as configurações feitas no switch:

```bash
wr mem
```

---

Agora, o seu switch Aruba 6100 está configurado com um hostname, endereço IP e SNMP corretamente configurados.
