---
title: Exemplo de compartilhamento de porta Net.TCP
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03da5959-0574-4e91-8a53-05854b6c55dc
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 7410f57d7b86bf719a368f1efcc8c82d41c82d11
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/02/2017
---
# <a name="nettcp-port-sharing-sample"></a><span data-ttu-id="74cf5-102">Exemplo de compartilhamento de porta Net.TCP</span><span class="sxs-lookup"><span data-stu-id="74cf5-102">Net.TCP Port Sharing Sample</span></span>
<span data-ttu-id="74cf5-103">O protocolo TCP/IP usa um número de 16 bits, chamado de porta, para diferenciar conexões para vários aplicativos de rede em execução no mesmo computador.</span><span class="sxs-lookup"><span data-stu-id="74cf5-103">The TCP/IP protocol uses a 16-bit number, called a port, to differentiate connections to multiple network applications running on the same machine.</span></span> <span data-ttu-id="74cf5-104">Se um aplicativo estiver escutando em uma porta, todo o tráfego TCP dessa porta irá para esse aplicativo.</span><span class="sxs-lookup"><span data-stu-id="74cf5-104">If an application is listening on a port, then all TCP traffic for that port goes to that application.</span></span> <span data-ttu-id="74cf5-105">Outros aplicativos não podem escutar na porta ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="74cf5-105">Other applications cannot listen on that port at the same time.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="74cf5-106">Os exemplos podem já estar instalados no seu computador.</span><span class="sxs-lookup"><span data-stu-id="74cf5-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="74cf5-107">Verifique o seguinte diretório (padrão) antes de continuar.</span><span class="sxs-lookup"><span data-stu-id="74cf5-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="74cf5-108">Se este diretório não existir, vá para [Windows Communication Foundation (WCF) e exemplos do Windows Workflow Foundation (WF) para o .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) para baixar todos os [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] e [!INCLUDE[wf1](../../../../includes/wf1-md.md)] exemplos.</span><span class="sxs-lookup"><span data-stu-id="74cf5-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="74cf5-109">Este exemplo está localizado no seguinte diretório.</span><span class="sxs-lookup"><span data-stu-id="74cf5-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\PortSharing`  
  
 <span data-ttu-id="74cf5-110">Muitos protocolos têm um número de porta padrão ou padrão que eles usam.</span><span class="sxs-lookup"><span data-stu-id="74cf5-110">Many protocols have a standard or default port number that they use.</span></span> <span data-ttu-id="74cf5-111">Por exemplo, o protocolo HTTP normalmente usa a porta TCP 80.</span><span class="sxs-lookup"><span data-stu-id="74cf5-111">For example, the HTTP protocol typically uses TCP port 80.</span></span> <span data-ttu-id="74cf5-112">Serviços de informações da Internet (IIS) tem um ouvinte para compartilhar uma porta entre vários aplicativos de HTTP.</span><span class="sxs-lookup"><span data-stu-id="74cf5-112">Internet Information Services (IIS) has a listener to share a port between multiple HTTP applications.</span></span> <span data-ttu-id="74cf5-113">O IIS escuta na porta diretamente e encaminha mensagens para o aplicativo apropriado com base nas informações dentro do fluxo de mensagens.</span><span class="sxs-lookup"><span data-stu-id="74cf5-113">IIS listens on the port directly and forwards messages to the appropriate application based on information inside the message stream.</span></span> <span data-ttu-id="74cf5-114">Isso permite que vários aplicativos HTTP usar o mesmo número de porta sem a necessidade de competir para reservar uma porta para receber mensagens.</span><span class="sxs-lookup"><span data-stu-id="74cf5-114">This allows multiple HTTP applications to use the same port number without having to compete to reserve the port for receiving messages.</span></span>  
  
 <span data-ttu-id="74cf5-115">Compartilhamento de porta NetTcp é um [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]recurso que permite da mesma forma que vários aplicativos de rede compartilhar uma única porta.</span><span class="sxs-lookup"><span data-stu-id="74cf5-115">NetTcp Port Sharing is a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]feature that similarly allows multiple network applications to share a single port.</span></span> <span data-ttu-id="74cf5-116">O serviço de compartilhamento de porta NetTcp aceita conexões usando o protocolo NET. TCP e encaminha mensagens com base em seu endereço de destino.</span><span class="sxs-lookup"><span data-stu-id="74cf5-116">The NetTcp Port Sharing Service accepts connections using the net.tcp protocol and forwards messages based on their destination address.</span></span>  
  
 <span data-ttu-id="74cf5-117">O serviço de compartilhamento de porta NetTcp não é habilitado por padrão.</span><span class="sxs-lookup"><span data-stu-id="74cf5-117">The NetTcp Port Sharing Service is not enabled by default.</span></span> <span data-ttu-id="74cf5-118">Antes de executar este exemplo, você deve habilitar manualmente o serviço.</span><span class="sxs-lookup"><span data-stu-id="74cf5-118">Before running this sample, you must manually enable the service.</span></span> <span data-ttu-id="74cf5-119">Para obter mais informações, consulte [como: habilitar o serviço de compartilhamento de porta NET. TCP](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="74cf5-119">For more information, see [How to: Enable the Net.TCP Port Sharing Service](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md).</span></span> <span data-ttu-id="74cf5-120">Se o serviço estiver desabilitado, uma exceção é lançada quando o aplicativo de servidor é iniciado.</span><span class="sxs-lookup"><span data-stu-id="74cf5-120">If the service is disabled, an exception is thrown when the server application is started.</span></span>  
  
```  
Unhandled Exception: System.ServiceModel.CommunicationException: The TransportManager failed to listen on the supplied URI using the NetTcpPortSharing service: failed to start the service because it is disabled. An administrator can enable it by running 'sc.exe config NetTcpPortSharing start= demand'.. ---> System.InvalidOperationException: Cannot start service NetTcpPortSharing on computer '.'. ---> System.ComponentModel.Win32Exception: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it  
```  
  
 <span data-ttu-id="74cf5-121">Compartilhamento de porta está habilitado no servidor, definindo a <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> propriedade o <xref:System.ServiceModel.NetTcpBinding> associação ou o <xref:System.ServiceModel.Channels.TcpTransportBindingElement> elemento de associação.</span><span class="sxs-lookup"><span data-stu-id="74cf5-121">Port sharing is enabled on the server by setting the <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> property of the <xref:System.ServiceModel.NetTcpBinding> binding or the <xref:System.ServiceModel.Channels.TcpTransportBindingElement> binding element.</span></span> <span data-ttu-id="74cf5-122">O cliente não precisa saber como compartilhamento de porta foi configurado para usá-lo no servidor.</span><span class="sxs-lookup"><span data-stu-id="74cf5-122">The client does not have to know how port sharing has been configured to use it on the server.</span></span>  
  
## <a name="enabling-port-sharing"></a><span data-ttu-id="74cf5-123">Habilitar o compartilhamento de porta</span><span class="sxs-lookup"><span data-stu-id="74cf5-123">Enabling Port Sharing</span></span>  
 <span data-ttu-id="74cf5-124">O código a seguir demonstra como habilitar compartilhamento de porta no servidor.</span><span class="sxs-lookup"><span data-stu-id="74cf5-124">The following code demonstrates enabling port sharing on the server.</span></span> <span data-ttu-id="74cf5-125">Ele inicia uma instância do `ICalculator` serviço em uma porta fixa com um caminho URI aleatório.</span><span class="sxs-lookup"><span data-stu-id="74cf5-125">It starts an instance of the `ICalculator` service on a fixed port with a random URI path.</span></span> <span data-ttu-id="74cf5-126">Embora os dois serviços podem compartilhar a mesma porta, os endereços de ponto de extremidade geral ainda devem ser exclusivos para que o serviço de compartilhamento de porta NetTcp pode encaminhar mensagens para o aplicativo correto.</span><span class="sxs-lookup"><span data-stu-id="74cf5-126">Even though two services can share the same port, their overall endpoint addresses still must be unique so that the NetTcp Port Sharing Service can route messages to the correct application.</span></span>  
  
```  
// Configure a binding with TCP port sharing enabled  
NetTcpBinding binding = new NetTcpBinding();  
binding.PortSharingEnabled = true;  
  
// Start a service on a fixed TCP port  
ServiceHost host = new ServiceHost(typeof(CalculatorService));  
ushort salt = (ushort)new Random().Next();  
string address =  
   String.Format("net.tcp://localhost:9000/calculator/{0}", salt);  
host.AddServiceEndpoint(typeof(ICalculator), binding, address);  
host.Open();  
```  
  
 <span data-ttu-id="74cf5-127">Com o compartilhamento de porta habilitado, você pode executar o serviço várias vezes sem ter um conflito de número de porta.</span><span class="sxs-lookup"><span data-stu-id="74cf5-127">With port sharing enabled, you can run the service multiple times without having a conflict over the port number.</span></span> <span data-ttu-id="74cf5-128">Se você alterar o código para desabilitar o compartilhamento de porta, iniciar duas cópias do serviço resulta em falha do segundo com um <xref:System.ServiceModel.AddressAlreadyInUseException>.</span><span class="sxs-lookup"><span data-stu-id="74cf5-128">If you change the code to disable port sharing, starting up two copies of the service results in the second failing with an <xref:System.ServiceModel.AddressAlreadyInUseException>.</span></span>  
  
```  
Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000.  Make sure that you are not trying to use this endpoint multiple times in your application and that there are no other applications listening on this endpoint. ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="74cf5-129">Executando o exemplo</span><span class="sxs-lookup"><span data-stu-id="74cf5-129">Running the Sample</span></span>  
 <span data-ttu-id="74cf5-130">Você pode usar o cliente de teste para verificar se as mensagens são roteadas corretamente nos serviços de compartilhamento de porta.</span><span class="sxs-lookup"><span data-stu-id="74cf5-130">You can use the test client to check that messages are correctly routed to services sharing the port.</span></span>  
  
```  
class client  
{  
   static void Main(string[] args)  
   {  
      Console.Write("Enter the service number to test: ");  
      ushort salt = ushort.Parse(Console.ReadLine());  
      string address = String.Format("net.tcp://localhost:9000/calculator/{0}", salt);  
      ChannelFactory<ICalculator> factory = new ChannelFactory<ICalculator>(new NetTcpBinding());  
      ICalculator proxy = factory.CreateChannel(new EndpointAddress(address));  
  
      // Call the Add service operation.  
      double value1 = 100.00D;  
      double value2 = 15.99D;  
      double result = proxy.Add(value1, value2);  
      Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Subtract service operation.  
      value1 = 145.00D;  
      value2 = 76.54D;  
      result = proxy.Subtract(value1, value2);  
      Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Multiply service operation.  
      value1 = 9.00D;  
      value2 = 81.25D;  
      result = proxy.Multiply(value1, value2);  
      Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Divide service operation.  
      value1 = 22.00D;  
      value2 = 7.00D;  
      result = proxy.Divide(value1, value2);  
      Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
      Console.WriteLine();  
      Console.WriteLine("Press <ENTER> to terminate client.");  
      Console.ReadLine();  
  
      factory.Close();  
   }  
}  
```  
  
 <span data-ttu-id="74cf5-131">Cada instância do serviço imprime seu número exclusivo e um endereço.</span><span class="sxs-lookup"><span data-stu-id="74cf5-131">Each instance of the service prints out its unique number and address.</span></span> <span data-ttu-id="74cf5-132">Por exemplo, você verá o seguinte texto ao executar service.exe.</span><span class="sxs-lookup"><span data-stu-id="74cf5-132">For instance, you may see the following text when you run service.exe.</span></span>  
  
```  
Service #4381 listening on net.tcp://localhost:9000/calculator/4381.  
Press <ENTER> to terminate service.  
```  
  
 <span data-ttu-id="74cf5-133">Insira o número de serviço que você vê aqui quando você executar client.exe.</span><span class="sxs-lookup"><span data-stu-id="74cf5-133">Enter the service number you see here when you run client.exe.</span></span>  
  
```  
Enter the service number to test: 4381  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="74cf5-134">Este exemplo pode ser executado em uma configuração de várias máquinas alterando o endereço gerado que o cliente usa.</span><span class="sxs-lookup"><span data-stu-id="74cf5-134">This sample can be run in a cross-machine configuration by changing the generated address that the client uses.</span></span> <span data-ttu-id="74cf5-135">Em Client.cs, altere a cadeia de caracteres de formato de endereço de ponto de extremidade para coincidir com o novo endereço do seu serviço.</span><span class="sxs-lookup"><span data-stu-id="74cf5-135">In the Client.cs, change the endpoint address format string to match the new address of your service.</span></span> <span data-ttu-id="74cf5-136">Substitua todas as referências a "localhost" com o endereço IP da máquina do servidor.</span><span class="sxs-lookup"><span data-stu-id="74cf5-136">Replace any references to "localhost" with the IP address of the server machine.</span></span> <span data-ttu-id="74cf5-137">Você deve recompilar o exemplo depois de fazer essa alteração.</span><span class="sxs-lookup"><span data-stu-id="74cf5-137">You must recompile the sample after making this change.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="74cf5-138">Para configurar, compilar, e executar o exemplo</span><span class="sxs-lookup"><span data-stu-id="74cf5-138">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="74cf5-139">Instalar [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 usando o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="74cf5-139">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="74cf5-140">Certifique-se de que você executou o [único procedimento de instalação para os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="74cf5-140">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="74cf5-141">Habilite NetTcp porta de serviço de compartilhamento do conforme descrito anteriormente na seção Introdução.</span><span class="sxs-lookup"><span data-stu-id="74cf5-141">Enable the NetTcp Port Sharing Service as previously described in the introduction section.</span></span>  
  
4.  <span data-ttu-id="74cf5-142">Para compilar o c# ou Visual Basic .NET edição da solução, siga as instruções em [compilar os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="74cf5-142">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="74cf5-143">Para executar o exemplo em uma configuração ou entre computadores, siga as instruções em [executando os exemplos do Windows Communication Foundation](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="74cf5-143">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="74cf5-144">Detalhes específicos para executar este exemplo estão incluídos anteriormente em execução a seção de exemplo.</span><span class="sxs-lookup"><span data-stu-id="74cf5-144">Specific details for running this sample are included previously in the Running the Sample section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="74cf5-145">Consulte também</span><span class="sxs-lookup"><span data-stu-id="74cf5-145">See Also</span></span>