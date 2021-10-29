# App
 basic docker console .netcore

caso deseje executar no windows precisa ter o docker instalado, para isso instale o docker desktop, mas antes execute os seguintes passos.
--Abra o PowerShell como administrador e execute:
---dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart
este comando irá habilitar o WSL
--dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart
este comando  irá habilitar o WSL2
atualize o kernel no seguinte link https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi
defina o WSL2 como padrão
--wsl --set-default-version 2

após estas etapas reinicia a sua máquina.
agora é só instalar o docker desktop e depois executar os seguintes comandos para executar o docker.
lembrando que estes comandos tem que ser executados dentro da pasta App, onde se encontra o dockerfile
--docker build -t counter-image -f Dockerfile .

--docker create --name core-counter counter-image

--docker start core-counter

para visualizar que o resultado execute o seguinte comando 
--docker attach --sig-proxy=false core-counter

--docker stop core-counter

