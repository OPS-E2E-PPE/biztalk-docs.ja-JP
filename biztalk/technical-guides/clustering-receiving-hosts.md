---
title: "受信ホストをクラスタ リング |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 93544f39-836f-4a4f-9587-230bfa3a9d4e
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 876cdb5f3740e5f06d00a536e1459c64ac886d89
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="clustering-receiving-hosts"></a>受信ホストをクラスタ リング
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]BizTalk ホスト内のクラスター リソースとして構成できるようにする機能を提供する[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター グループ。 ホスト クラスターのサポートをサポートする受信高可用性を統合 BizTalk アダプターを複数のホスト インスタンスで、同時が実行されない、FTP 受信ハンドラーなど、特定の状況では、POP3 受信ハンドラーに提供されます。 MSMQ サービスのクラスター化が必要となるような状況でも、MSMQ アダプターによって送受信されたメッセージについて、トランザクションの一貫性を確実に保つことができます。  
  
> [!NOTE]  
>  ホスト クラスタ リングはでのみ使用可能な[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]Enterprise Edition。  
  
> [!NOTE]  
>  前に、クラスター化できるは、BizTalk ホストを構成には、少なくとも 2 つ[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のメンバーとして、BizTalk グループ内のコンピューター、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター。 構成の詳細については、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスターは、「 [、、Windows Server 2008 のクラスタ リング ドキュメント、ホワイト ペーパーは、web キャスト グループ](http://go.microsoft.com/fwlink/?LinkId=156818)(http://go.microsoft.com/fwlink/?LinkId=156818).  
  
 BizTalk ホストのクラスター サポートを統合 BizTalk アダプターのうち 5 つの高可用性を実現する使用可能な: FTP アダプター、MSMQ アダプター、POP3 アダプター、SQL アダプターおよび SAP アダプター。 また、順次配送の目的でアダプターの単一インスタンスを実行する場合に、ホスト クラスター サポートを利用して高い可用性を実現できます。  
  
 すべての BizTalk アダプター ハンドラーは、クラスター化されたホストで実行できますが、以下の説明に従って以外のクラスター ホストでアダプター ハンドラーの実行からの利点はありません。 処理の要件には、以下のセクションで説明するシナリオのいずれかが含まれている場合は、クラスター化されたホストでアダプター ハンドラーを実行する必要があります。 設定の詳細な手順について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]クラスターを参照してください[Improving Fault Tolerance in Windows Server 2008 フェールオーバー クラスターまたは Windows Server 2003 サーバー クラスターを使用して BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=156819) (http://go.microsoft.com/fwlink/?LinkId=156819)。  
  
## <a name="scenarios-for-running-adapter-handlers-in-clustered-hosts"></a>クラスター化されたホストでアダプター ハンドラーを実行するためのシナリオ  
 処理の要件には、以下に示すシナリオのいずれかが含まれている場合は、クラスター化されたホストでアダプター ハンドラーを実行する必要があります。  
  
-   クラスター化された BizTalk ホストで FTP アダプターの受信ハンドラーを実行する  
  
-   クラスター化された BizTalk ホストで MSMQ アダプター ハンドラーを実行する  
  
-   クラスター化された BizTalk ホストで POP3 アダプターの受信ハンドラーを実行する  
  
-   クラスター化された BizTalk ホストで順次配送をサポートする受信アダプターを実行する  
  
 これらのシナリオの詳細については、次を参照してください。[化されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](http://go.microsoft.com/fwlink/?LinkId=151284)(http://go.microsoft.com/fwlink/?LinkId=151284)。  
  
## <a name="see-also"></a>参照  
 [スケール アウト受信ホスト](../technical-guides/scaling-out-receiving-hosts.md)   
 [スケール アウト処理の各ホスト](../technical-guides/scaling-out-processing-hosts.md)   
 [スケール アウト送信ホスト](../technical-guides/scaling-out-sending-hosts.md)