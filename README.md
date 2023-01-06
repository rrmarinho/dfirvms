# Curso DFIR - Preparaçao do Lab
Digital Forensics and Incident Response

### 1. Objetivo 
  
  O objetivo deste conteúdo é fornecer um passo a passo para a preparação do ambiente de laboratório para o curso de DFIR. O conteúdo está dividido nas seguintes seções:
  
  - [**Pré-requisitos**](https://github.com/rrmarinho/dfirvms/edit/main/README.md#2-pr%C3%A9-requisito-vmware-workstation-pro): detalhamento de requisitos de software e hardware;
  
  - [**Preparação da VM Windows 10 Workstation**](https://github.com/rrmarinho/dfirvms/edit/main/README.md#3-prepara%C3%A7%C3%A3o-vm-windows-10): Licença de avaliação fornecida pela Microsoft com validade de 90 dias;

  - [**Preparação da VM SANS SIFT Workstation**](https://github.com/rrmarinho/dfirvms/edit/main/README.md#4-prepara%C3%A7%C3%A3o-vm-sift-workstation): distribuição Linux com ferramentas pré-instaladas voltadas para análises forense mantida pela SANS;
  
  - [**Download de artefatos para análise**](): imagens de disco, memória e tráfego de rede que  serão utilizados nas análises.

### 2. Pré-requisitos:  

#### Hardware

  - Processador: um processador recente é requerido para este curso. Recomendado: CPU: 64-bit Intel i5/i7 (4th generation+) - x64 bit 2.0+ GHz ou superior;
  - Memória: 16GB ou superior. 
  - Disco: 200GB livres. Este espaço pode estar no disco do próprio sistema ou em discos externos.

#### Software

 - VMware Workstation Pro
    - Caso ainda não tenha o Vmware na sua estação de trabalho, você pode obter e instalar uma licença de avaliação válida por 30 dias em:

      - Download VMware Workstation Pro: https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html

      - O arquivo tem aproximadamente 600MB;

      - Não requer registro;
      
        <img src="https://user-images.githubusercontent.com/32780523/210852367-14caa99a-9799-44ed-8236-344037975fe5.png" width=50% height=50%>


### 3. Preparação da VM Windows 10

<img src="https://user-images.githubusercontent.com/32780523/210851615-6b0dcf8f-5a85-4339-9ca4-359be1ad24a7.png" width=80% height=80%>

1. Faça o download da VM Windows no site da Microsoft: https://developer.microsoft.com/en-us/microsoft-edge/tools/vms/

    - Escolha a as opções:
      - MSEdge on Windows 10 (x64) Stable 1809
      - VMWare (Windows, Mac)

    - Este arquivo tem aproximadamente 7GB.

2. Importe a VM Windows para o seu virtualizador VMware:

    - Descompacte o arquivo zip da VM:
    
        <img src="https://user-images.githubusercontent.com/32780523/210853051-df3efc7c-d9c0-499a-b081-2e7841c2fa67.png" width=50% height=50%>
    
         
    - Clique 2x no MSEdge-Win10-Vmware.ovf. O arquivo será aberto no VMware Workstation e solicitará informações para importar a VM. Indique um nome (VM Windows) e um local para armazená-la e clique em “Import”. Exemplo:

      <img src="https://user-images.githubusercontent.com/32780523/210853212-70a46f9b-c368-4c2f-9a21-92aff26c996f.png" width=40% height=40%>
      
3. Crie um primeiro snapshot da sua VM para preservar o estado inicial:

     - Clique com o botão direito na VM Windows;

	   - Menu Snapshot -> Take Snapshot;
      
        
        <img src="https://user-images.githubusercontent.com/32780523/210853420-759c3d33-fd8e-4b7f-a7cd-a1aa6c2634d4.png" width=30% height=30%>
      
	   - Dê um nome para o snapshot (ex: Estado inicial) e crie-o.
      
          <img src="https://user-images.githubusercontent.com/32780523/210853445-d6c1b398-c9df-4201-9a0f-c1076bd4d8c6.png" width=30% height=30%>
 
4. Inicie a VM Windows:
 
    - Selecione a VM Windows e clique no botão “Start”, conforme imagem:
    
      <img src="https://user-images.githubusercontent.com/32780523/210855782-b8b82f0c-dc4a-4473-8169-eb89ecfae3b5.png" width=50% height=50%>
 
5. Logando na VM Windows:
 
    - Usuário: IEUser
    - Senha: Passw0rd!
    
      <img src="https://user-images.githubusercontent.com/32780523/210856023-b02261dc-b50c-479e-a2e7-a0478c1a7683.png" width=50% height=50%>


6. Instale o VMware Tools:
  
  
      - Menu VM -> Install VMware Tools:
    
          <img src="https://user-images.githubusercontent.com/32780523/210856354-c8711b08-9dd6-4060-9d15-4b1ac92b2720.png" width=50% height=50%>

      - Na VM, abra o explorer e clique na unidade D:\ (CDROM):
    
          <img src="https://user-images.githubusercontent.com/32780523/210856542-28dcd97d-9226-4f4b-bedc-a14a91b89f13.png" width=50% height=50%>

      - Na sequencia, clique em "Yes" e siga os passos do setup. Caso apareça uma mensagem de erro de um setup já em andamento, cancele e inicie a instalação clicando na unidade D:\ novamente.
    
          <img src="https://user-images.githubusercontent.com/32780523/210856673-3e575271-82a7-41f0-91e4-6cfee4f3913b.png" width=50% height=50%>

      - Ao final, reinicie a VM Windows.
      
7. Faça o download do pacote de ferramentas que utilizaremos na VM Windows:

    - [Download do pacote Tools.zip](https://mega.nz/file/nvp12bIS#dar_C6JTu-R6OXq5rZcNKFvMpvJkdRGXYrMVfkGFuwc)

    - Este pacote tem aproximadamente 5.5GB compactados.

    - Descompacte o arquivo em um diretório de sua escolha.
    
      <img src="https://user-images.githubusercontent.com/32780523/210858188-b0ef2e2f-f190-4cf5-b710-4171a3e94ce8.png" width=50% height=50%>

8. Mapeie o diretório “Tools” na sua VM para acessar os arquivos:

    - Menu VM -> Settings;

      <img src="https://user-images.githubusercontent.com/32780523/210858517-dd0bda30-206e-49fc-942a-04aac20a50e1.png" width=50% height=50%>
  
    - Options -> Shared Folders -> Always enabled -> Add...
    
      <img src="https://user-images.githubusercontent.com/32780523/210858545-93ca3607-819d-4c6a-aa0f-0fca604b3463.png" width=50% height=50%>
    
    - Selecione o diretório “Tools” do host e avance

      <img src="https://user-images.githubusercontent.com/32780523/210858572-b72484fa-6493-4643-b6e9-6759e5c84383.png" width=50% height=50%>

    - Ao final do processo, os arquivos podem ser acessados no diretório mapeado:
    
      <img src="https://user-images.githubusercontent.com/32780523/210858977-84692dbc-6d19-4cd7-9df7-0fe11fd9f28d.png" width=50% height=50%>
      
9. Instale as ferramentas:

  - Instale as ferramentas por meio dos arquivos de setup:
    
    - Autopsy;
    - Wireshark;
    - OSFMount;
    - Event Log Explorere (elex_setup.exe);

  - Extraia a ferramenta Timeline Explorer:
  
    - Crie um diretório chamado “Tools” no Desktop:
    
    - Descompacte o conteúdo do arquivo TimelineExplorer.zip no diretório Tools no Desktop:
    
      <img src="https://user-images.githubusercontent.com/32780523/210859546-f8697673-dfbc-466b-9f6c-04fa8ee76afc.png" width=50% height=50%>

  - Descompacte o conteúdo do arquivo FTK_Imager.zip também no diretório Tools no Desktop.

10. Uma vez instaladas as ferramentas, recomendo que crie um segundo snapshot.

    <img src="https://user-images.githubusercontent.com/32780523/210860400-bdac4de6-9d59-4f65-ba89-32f15f6cc3c2.png" width=30% height=30%>

11. A VM Windows está pronta. Pode desligá-la ou suspendê-la.

### 4. Preparação da VM SIFT Workstation

<img src="https://user-images.githubusercontent.com/32780523/210861212-788ddfa3-9906-4317-a75d-00059b829e25.png" width=80% height=80%>

1. Faça o download da VM SIFT Workstation no site da SANS:

    - https://www.sans.org/tools/sift-workstation/
    
      - Você precisará criar uma conta e logar no site;
      
      - Depois escolha a opção Download SIFT Workstation VM Appliance. O arquivo tem aprox. 3.5 GB.
      
        <img src="https://user-images.githubusercontent.com/32780523/210861736-4d684f11-8875-4851-838c-3e59c027f8ac.png" width=70% height=70%>
        
2. Importe a VM SIFT Workstation:

    - Clique 2x no arquivo baixado (SIFT-Workstation.ova);
    
    - Indique o nome da VM (SIFT Workstation) e um local para onde deve ser importada no seu host:
    
      <img src="https://user-images.githubusercontent.com/32780523/210862099-77884fa5-ccef-4526-9704-65e522a7e822.png" width=40% height=40%>
      
    - Após a importação, crie um snapshot da VM para preservar seu estado inicial.
    
3. Inicie a VM:

    - Para logar, utilize as credenciais:
    
        - Usuário: sansforensics
        - Senha: forensics
    
       <img src="https://user-images.githubusercontent.com/32780523/210862317-9adda993-b38d-48f7-9a5f-c5d9e57d91fb.png" width=40% height=40%>

4. A VM SIFT Workstation está pronta. Você pode desliga-la ou suspendê-la.


### 5. Download de artefatos

Faça o download de um [arquivo ZIP contendo artefatos]() de disco, memória e tráfego de rede que serão utilzados nas análises. 

Hash MD5 do arquivo: 15c9583fcf377481d4eb56d1e782e0b4

OBS: O ZIP tem uma senha que será disponibilizada durante a aula. 










    


    
    



      



  














