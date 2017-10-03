---
title: "停止および開始オーケストレーション、送信ポート、および受信場所をプログラムによって |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- orchestrations, examples
- examples, orchestrations
- send ports, examples
- SDK samples, send ports
- examples, send ports
- SDK samples, orchestrations
- receive locations
- SDK samples, receive locations
- examples, receive locations
ms.assetid: 1c06e14d-44ec-4292-a2c2-ee2c8d07d948
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 96b914129d9afb6dfd542f00a302e739e34dafbe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="stopping-and-starting-orchestrations-send-ports-and-receive-locations-programmatically"></a><span data-ttu-id="3c31c-102">停止および開始オーケストレーション、送信ポート、および受信場所をプログラムで</span><span class="sxs-lookup"><span data-stu-id="3c31c-102">Stopping and Starting Orchestrations, Send Ports, and Receive Locations Programmatically</span></span>
<span data-ttu-id="3c31c-103">ここでは、プログラミングによってオーケストレーション、送信ポート、および受信場所を停止および開始するサンプル コードを紹介します。</span><span class="sxs-lookup"><span data-stu-id="3c31c-103">This topic provides sample code for programmatically stopping and starting orchestrations, send ports, and receive locations.</span></span> <span data-ttu-id="3c31c-104">これらのアクションは、すべてのオーケストレーション、送信ポート、および受信場所で、個々にまたは複数同時に実行することができます。</span><span class="sxs-lookup"><span data-stu-id="3c31c-104">You can perform these actions on all orchestrations, send ports, and receive locations as a group or individually.</span></span> <span data-ttu-id="3c31c-105">このコードをプログラムに組み込んで、これらのアクションを動的に実行できます。</span><span class="sxs-lookup"><span data-stu-id="3c31c-105">You can include this code in a program to perform these actions dynamically.</span></span> <span data-ttu-id="3c31c-106">デザイン時に、グラフィカル ユーザー インターフェイスでアクションを実行する[!INCLUDE[btsCoName](../../includes/btsconame-md.md)] [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)]、または BizTalk 管理コンソールで実行時にします。</span><span class="sxs-lookup"><span data-stu-id="3c31c-106">You perform these actions in the graphical user interface at design time in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)], or at run time in the BizTalk Administration console.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3c31c-107">オーケストレーションを開始または停止するコードの場合、オーケストレーション、送信ポート、または受信場所を指定する必要はありません。</span><span class="sxs-lookup"><span data-stu-id="3c31c-107">For the code to start and stop orchestrations, you do not have to designate the orchestrations, send ports, or receive locations.</span></span> <span data-ttu-id="3c31c-108">サンプル コードは、セットアップ時に [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] によってインストールされたすべてのオーケストレーション、送信ポート、および受信場所でアクションを実行します。</span><span class="sxs-lookup"><span data-stu-id="3c31c-108">The sample code performs the action on all orchestrations, send ports, and receive locations that [!INCLUDE[BTARN_CurrentVersion_abbrev](../../includes/btarn-currentversion-abbrev-md.md)] installed at set up.</span></span> <span data-ttu-id="3c31c-109">単一のオーケストレーション、送信ポート、または受信場所でアクションを実行するコードの場合、コードを実行するオーケストレーション、送信ポート、または受信場所を指定するパラメーターを追加します。</span><span class="sxs-lookup"><span data-stu-id="3c31c-109">For the code that acts on a single orchestration, send port, or receive location, add a parameter indicating on which orchestration, send port, or receive location you want the code to run.</span></span>  
  
## <a name="demonstrates"></a><span data-ttu-id="3c31c-110">使用例</span><span class="sxs-lookup"><span data-stu-id="3c31c-110">Demonstrates</span></span>  
 <span data-ttu-id="3c31c-111">このトピックのサンプル コードには、以下のアクションを実行する個別のコード セクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c31c-111">The sample code in this topic includes separate code sections to do the following:</span></span>  
  
-   <span data-ttu-id="3c31c-112">オーケストレーションの開始 — すべての送信ポートおよび受信場所を開始し、すべてのオーケストレーションを登録して開始します。</span><span class="sxs-lookup"><span data-stu-id="3c31c-112">Start orchestrations—start all the send ports and receive locations, and enlist and start all orchestrations</span></span>  
  
-   <span data-ttu-id="3c31c-113">オーケストレーションの停止 — すべてのオーケストレーションと送信ポートの登録を解除し、すべての受信場所を無効にします。</span><span class="sxs-lookup"><span data-stu-id="3c31c-113">Stop orchestrations—unenlist all orchestrations, unenlist all send ports, and disable all receive locations</span></span>  
  
-   <span data-ttu-id="3c31c-114">単一の送信ポートの開始</span><span class="sxs-lookup"><span data-stu-id="3c31c-114">Start a single send port</span></span>  
  
-   <span data-ttu-id="3c31c-115">単一の受信場所の有効化</span><span class="sxs-lookup"><span data-stu-id="3c31c-115">Enable a single receive location</span></span>  
  
-   <span data-ttu-id="3c31c-116">単一の送信ポートの登録解除</span><span class="sxs-lookup"><span data-stu-id="3c31c-116">Unenlist a single send port</span></span>  
  
-   <span data-ttu-id="3c31c-117">単一の受信場所の無効化</span><span class="sxs-lookup"><span data-stu-id="3c31c-117">Disable a single receive location</span></span>  
  
-   <span data-ttu-id="3c31c-118">単一のオーケストレーションの開始</span><span class="sxs-lookup"><span data-stu-id="3c31c-118">Start a single orchestration</span></span>  
  
-   <span data-ttu-id="3c31c-119">単一のオーケストレーションの登録解除</span><span class="sxs-lookup"><span data-stu-id="3c31c-119">Unenlist a single orchestration</span></span>  
  
## <a name="example"></a><span data-ttu-id="3c31c-120">例</span><span class="sxs-lookup"><span data-stu-id="3c31c-120">Example</span></span>  
 <span data-ttu-id="3c31c-121">このトピックのサンプル コードには、「デモ」セクションに一覧表示されている機能を実行する個別のコード セクションが含まれています。</span><span class="sxs-lookup"><span data-stu-id="3c31c-121">The sample code in this topic includes separate code sections to do the functions listed in the "Demonstrates" section.</span></span>  
  
```  
using System;  
using Microsoft.BizTalk.ExplorerOM;  
  
namespace Control  
{  
class Control  
{  
BtsCatalogExplorer bceExplorer;  
string[] sOrchestrations;  
string[] sReceiveLocations;  
string[] sSendPorts;  
  
[STAThread]  
static void Main(string[] args)  
{  
Control controlInstance = new Control();  
if(args.Length>0 && args[0].ToUpper()=="STOP")  
controlInstance.StopOrchestrations();  
else  
controlInstance.StartOrchestrations();  
}  
  
public Control()  
{  
bceExplorer = new BtsCatalogExplorer();  
//Edit the following connection string to point to the correct database and server  
bceExplorer.ConnectionString = "Integrated Security=SSPI;database=BizTalkMgmtDb;server=localhost";  
  
//Orchestrations  
sOrchestrations = new string[9];  
sOrchestrations[0]="Microsoft.Solutions.BTARN.CommonTypes.OdxTypes,Microsoft.Solutions.BTARN.CommonTypes, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[1]="Microsoft.Solutions.BTARN.CommonTypes.SendExceptionToLOB,Microsoft.Solutions.BTARN.CommonTypes, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[2]="Microsoft.Solutions.BTARN.CommonTypes.SendExceptionToPrivateProcess,Microsoft.Solutions.BTARN.CommonTypes, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[3]="Microsoft.Solutions.BTARN.PrivateInitiator.PrivateInitiatorProcess,Microsoft.Solutions.BTARN.PrivateInitiator, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[4]="Microsoft.Solutions.BTARN.PrivateResponder.PrivateResponderProcess,Microsoft.Solutions.BTARN.PrivateResponder, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[5]="Microsoft.Solutions.BTARN.PublicInitiator.PublicInitiatorV11,Microsoft.Solutions.BTARN.PublicInitiator, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[6]="Microsoft.Solutions.BTARN.PublicInitiator.PublicInitiatorProcess,Microsoft.Solutions.BTARN.PublicInitiator, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[7]="Microsoft.Solutions.BTARN.PublicResponder.PublicResponderV11,Microsoft.Solutions.BTARN.PublicResponder, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
sOrchestrations[8]="Microsoft.Solutions.BTARN.PublicResponder.PublicResponderProcess,Microsoft.Solutions.BTARN.PublicResponder, Version=3.3.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35";  
  
//Send Ports  
sSendPorts = new string[2];  
sSendPorts[0]="PrivateInitiator_To_LOB";  
sSendPorts[1]="PrivateResponder_To_LOB";  
  
//Receive Locations  
sReceiveLocations = new string[4];  
sReceiveLocations[0]="LOB_To_PrivateInitiator";  
sReceiveLocations[1]="LOB_To_PrivateResponder";  
sReceiveLocations[2]="RNIF_Async_Receive";  
sReceiveLocations[3]="RNIF_Sync_Receive";  
}  
  
public void StartOrchestrations()  
{     
bool bSuccess=true;  
  
//Start all the send ports  
for(int i=0;i<sSendPorts.Length;i++)  
{  
Console.WriteLine("Starting send port: " + sSendPorts[i]);  
bSuccess=StartSendPort(sSendPorts[i]);  
}  
  
//Start all the receive locations  
for(int i=0;i<sReceiveLocations.Length;i++)  
{  
Console.WriteLine("Enabling receive location: " + sReceiveLocations[i]);  
bSuccess=EnableReceiveLocation(sReceiveLocations[i]);  
}  
  
//Enlist and start all orchestrations  
for(int i=0;i<sOrchestrations.Length;i++)  
{  
Console.WriteLine("Starting orchestration: " + sOrchestrations[i].Split(',')[0]);  
bSuccess=StartOrchestration(sOrchestrations[i]);  
}  
  
if(bSuccess)  
Console.WriteLine("All artifacts successfully started");  
else  
Console.WriteLine("Not all artifacts were started");  
}  
  
public void StopOrchestrations()  
{     
bool bSuccess=true;  
  
//Unenlist all orchestrations  
for(int i=sOrchestrations.Length-1;i>=0;i--)  
{  
Console.WriteLine("Unelisting orchestration: " + sOrchestrations[i].Split(',')[0]);  
bSuccess=UnenlistOrchestration(sOrchestrations[i]);  
}  
  
//Unenlist all the send ports  
for(int i=sSendPorts.Length-1;i>=0;i--)  
{  
Console.WriteLine("Unenlisting send port: " + sSendPorts[i]);  
bSuccess=UnenlistSendPort(sSendPorts[i]);  
}  
  
//Disable all the receive locations  
for(int i=sReceiveLocations.Length-1;i>=0;i--)  
{  
Console.WriteLine("Disabling receive location: " + sReceiveLocations[i]);  
bSuccess=DisableReceiveLocation(sReceiveLocations[i]);  
}  
  
if(bSuccess)  
Console.WriteLine("All artifacts successfully stopped");  
else  
Console.WriteLine("Not all artifacts were stopped");  
}  
  
public bool StartSendPort(string sSendPortName)  
{  
try  
{  
SendPort sp = bceExplorer.SendPorts[sSendPortName];  
sp.Status = PortStatus.Started;  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
public bool EnableReceiveLocation(string sReceivePortName)  
{  
try  
{  
ReceivePort rp = bceExplorer.ReceivePorts[sReceivePortName];  
              foreach(ReceiveLocation rl in rp.ReceiveLocations)  
rl.Enable = true;  
  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
public bool UnenlistSendPort(string sSendPortName)  
{  
try  
{  
SendPort sp = bceExplorer.SendPorts[sSendPortName];  
sp.Status = PortStatus.Bound;  
  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
public bool DisableReceiveLocation(string sReceivePortName)  
{  
try  
{  
ReceivePort rp = bceExplorer.ReceivePorts[sReceivePortName];  
  
foreach(ReceiveLocation rl in rp.ReceiveLocations)  
rl.Enable = false;  
  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
  
private bool StartOrchestration(string sOrchestrationName)  
{  
  
BtsAssemblyCollection btsAssemblyCollection = bceExplorer.Assemblies;  
  
foreach (Microsoft.BizTalk.ExplorerOM.BtsAssembly btsAssembly in btsAssemblyCollection)  
{  
if(sOrchestrationName.Split(',')[1]==btsAssembly.DisplayName.Split(',')[0])  
{  
foreach (Microsoft.BizTalk.ExplorerOM.BtsOrchestration btsOrchestration in btsAssembly.Orchestrations)  
{  
if(sOrchestrationName==btsOrchestration.AssemblyQualifiedName)  
{  
btsOrchestration.Status=OrchestrationStatus.Started;  
try  
{  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
}  
}  
}  
return false;  
}  
  
private bool UnenlistOrchestration(string sOrchestrationName)  
{  
  
BtsAssemblyCollection btsAssemblyCollection = bceExplorer.Assemblies;  
  
foreach (Microsoft.BizTalk.ExplorerOM.BtsAssembly btsAssembly in btsAssemblyCollection)  
{  
if(sOrchestrationName.Split(',')[1]==btsAssembly.DisplayName.Split(',')[0])  
{  
foreach (Microsoft.BizTalk.ExplorerOM.BtsOrchestration btsOrchestration in btsAssembly.Orchestrations)  
{  
if(sOrchestrationName==btsOrchestration.AssemblyQualifiedName)  
{  
btsOrchestration.AutoTerminateInstances=true;  
btsOrchestration.Status=OrchestrationStatus.Unenlisted;  
try  
{  
bceExplorer.SaveChanges();  
return true;  
}  
catch(Exception e)  
{  
Console.WriteLine(e.Message);  
bceExplorer.DiscardChanges();  
return false;  
}  
}  
}  
}  
}  
return false;  
}  
  
}  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="3c31c-122">参照</span><span class="sxs-lookup"><span data-stu-id="3c31c-122">See Also</span></span>  
 [<span data-ttu-id="3c31c-123">サンプル</span><span class="sxs-lookup"><span data-stu-id="3c31c-123">Samples</span></span>](../../adapters-and-accelerators/accelerator-rosettanet/samples3.md)