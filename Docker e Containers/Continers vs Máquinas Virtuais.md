![[Pasted image 20250106220506.png]]
# [[Máquinas Virtuais|Máquinas Virtuais (VMs)]]
Uma máquina virtual executa um sistema operacional completo, incluindo o kernel, e utiliza um hypervisor para gerenciar várias VMs em um mesmo hardware. Isso resulta em um maior consumo de recursos, maior tempo de inicialização e menor eficiência em termos de uso de memória e CPU.

O maior ponto negativo de uma VM é que muitas vezes precisamos rodar uma aplicação pequena de, por exemplo, 1MB. Mas, como precisamos instalar o sistema operacional, vamos precisar que a máquina tenha no mínimo, por exemplo, 4GB. Isso faz com que precisemos de muito recurso para rodar algo que, na prática, não fará uso de todo esse recurso.

# Containers
Os containers compartilham o kernel do sistema operacional do host, isolando apenas o aplicativo e suas dependências. Isso os torna significativamente mais leves, permitindo um uso mais eficiente de recursos e uma inicialização quase instantânea. Containers são ideais para cenários que exigem rápida escalabilidade e alta densidade de aplicativos em um único host.