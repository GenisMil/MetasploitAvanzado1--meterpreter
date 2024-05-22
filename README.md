# Metasploit Avanzado--meterpreter

Vamos a realizar una búsqueda de información sobre una herramienta que permite ejecutar y desarrollar exploits contra sistemas objetivo. La tarea estará enfocada en la vulnerabilidad CVE-2017-0144 -EternalBlue. Conocido como el exploit más duradero y dañino de todos los tiempos.

Aunque el exploit EternalBlue (denominado oficialmente MS17-010 por Microsoft) solo afecta a los sistemas operativos Windows, cualquier cosa que use el protocolo de intercambio de archivos SMBv1 (Server Message Block versión 1) está técnicamente en riesgo de ser objetivo de ransomware y otros ciberataques.

Herramientas para usar:
- Kali Linux
- Metasploitable
- Windows 7 – Windowsploitable

# CONFIGURACION DE LAS MAQUINAS VIRTUALES.
Adaptador Puente:



![Image](https://github.com/users/GenisMil/projects/1/assets/170514782/8de7ed48-9ac3-4792-991f-89b7cb38b490)


Se pone en adaptador puente a las máquinas virtuales para proporcionar una integración más estrecha y funcional con la red física, ofreciendo mayor flexibilidad y para que tenga una presencia real en la red para capturar tráfico, realizar análisis y pruebas de penetración. Un adaptador puente es esencial para estos escenarios.

ifconfig.
* IP KALI: 192.168.1.190
* IP METASPLOITBALE: 192.168.1.150
* IP WINDOWS 7- WINDOWSPLOITABLE: 192.168.1.155

Comprobamos que las dos máquinas (METASPLOITABLE . WINDOWS7) tienen conectividad entre si haciendo ping entre ellas

![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/fc641fe5-a959-427c-8fb8-b02f1ca81bd1)


# ESCANER DE RED NMAP.
Descubrimos puertos y servicios abiertos en la máquina objetivo.
![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/4026d0d8-3a52-4919-89c1-45eb5a6c8b80)

# METASPLOIT
# msfconsole

![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/8e67d235-f223-4b2d-9d75-31c4bb7d58cf)

Lo vamos a usar para buscar exploits, descargar payloads y ejecutarlos.

# Search EternalBlue
Hacemos la busqueda de la vulnerabilidad

![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/7972d50d-cfae-4c8f-8ad2-2018e57ac4a8)

Elegiremos la primera opción:

0 exploit/windows/smb/ms17_010_eternalblue  Description: MS17-010 EternalBlue SMB Remote Windows Kernel Pool Corruption

# use 0
![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/9eb23ba8-b108-4d19-9936-5c4dff4ebb89)

# set RHOSTS
Ponemos la IP del equipo remoto y se confirma con Show options este todo en orden
![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/6cf5d60b-2c4b-4350-ae11-41d2bfea3250)

# set payloads
Los payloads son componentes esenciales en la explotación de vulnerabilidades, permitiendo a los atacantes realizar acciones específicas en los sistemas comprometidos. La elección y ejecución correcta de un payload determinan en gran medida el éxito y el impacto de un ataque
![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/7515043d-3e68-4f39-9778-4f865c979882)

# exploit
Escojemos el payload 3 y exploit. Para explotar la vulnerabilidad
![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/5dbd5b38-bdec-4cd8-8ab7-5fe340b34cb5)


# COMANDOS DE METERPRETER EN SISTEMAS WINDOWS
Permite obtener una gran cantidad de información sobre un objetivo  comprometido, así como también manipular ciertas características del sistema objetivo.
Los comandos mas interesantes se listan a continuación:
colocando help:

![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/562fcf9d-24dc-4957-a237-94895c9f0c5f)

![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/f999ab07-e43c-4667-82fe-d57416378dd0)


  # - TIME
Se hace el cambio de manera muy sencilla
  ![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/e6a2379a-779a-42bb-bf49-5a4b5245f105)

![image](https://github.com/GenisMil/MetasploitAvanzado1--meterpreter/assets/170514782/5538a054-1dd1-43fe-829f-9d70523f9bcf)


Como se muestra con este comando basico se puede realizar un proceso de comunicación muy completo entre un objetivo y su atacante.
