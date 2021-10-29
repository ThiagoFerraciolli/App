# App
 basic docker console .netcore

caso deseje executar no windows precisa ter o docker instalado, para isso instale o docker desktop, mas antes execute os seguintes passos.<br />
--Abra o PowerShell como administrador e execute:<br />
---dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart<br />
este comando irá habilitar o WSL<br />
--dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart<br />
este comando  irá habilitar o WSL2<br />
atualize o kernel no seguinte link https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi<br />
defina o WSL2 como padrão<br />
--wsl --set-default-version 2<br />

após estas etapas reinicia a sua máquina.<br />
agora é só instalar o docker desktop e depois executar os seguintes comandos para executar o docker.<br />
lembrando que estes comandos tem que ser executados dentro da pasta App, onde se encontra o dockerfile<br />
--docker build -t counter-image -f Dockerfile .<br />

--docker create --name core-counter counter-image<br />

--docker start core-counter<br />

para visualizar que o resultado execute o seguinte comando <br />
--docker attach --sig-proxy=false core-counter<br />

--docker stop core-counter

