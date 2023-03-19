# Step (ขั้นตอน)
#### 1. Install kubectl

- installed, use this command   

        curl.exe -LO "https://dl.k8s.io/release/v1.26.0/bin/windows/amd64/kubectl.exe"
  
- Validate binary, use this command

        curl.exe -LO "https://dl.k8s.io/v1.26.0/bin/windows/amd64/kubectl.exe.sha256"
        
- Append kubectl to PATH environment variable

 ![image](https://user-images.githubusercontent.com/117457616/226189153-09f341de-d4f1-4590-be43-19cf9e04337f.png)
![image](https://user-images.githubusercontent.com/117457616/226189193-b38f9639-0317-42a2-8a27-d2b3558605c3.png)
 

- Test kubectl, use this command for view of version

        kubectl version --client
- or

        kubectl version --client --output=yaml
  
- clean up the installation files

        del kubectl.exe kubectl.exe.sha256
  
#### 2. Install minikube
- set spec minikube
![image](https://user-images.githubusercontent.com/117457616/226190129-5526cbf0-939e-4a1c-bffd-082de55d7e0a.png)
- install using Powershell

        New-Item -Path 'c:\' -Name 'minikube' -ItemType Directory -Force
        Invoke-WebRequest -OutFile 'c:\minikube\minikube.exe' -Uri 'https://github.com/kubernetes/minikube/releases/latest/download/minikube-windows-amd64.exe' -UseBasicParsing




- Add minikube.exe to PATH run Powershell as Admin
![image](https://user-images.githubusercontent.com/117457616/226190303-afcf2114-adb6-49e9-8e89-b216eae4a2ec.png)
- Use this command

            $oldPath = [Environment]::GetEnvironmentVariable('Path', [EnvironmentVariableTarget]::Machine)
            if ($oldPath.Split(';') -inotcontains 'C:\minikube'){ `
             [Environment]::SetEnvironmentVariable('Path', $('{0};C:\minikube' -f $oldPath), [EnvironmentVariableTarget]::Machine) `
            }
- Test command minikube
![image](https://user-images.githubusercontent.com/117457616/226190471-f740c3bd-6300-4548-afa5-455508fb8eee.png)

