---
title: 受信ホストをクラスタ リング |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93544f39-836f-4a4f-9587-230bfa3a9d4e
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a50a23fa3c3d5a5469d82f42e7b467524c2a1f81
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277268"
---
# <a name="clustering-receiving-hosts"></a>受信ホストをクラスタ リング
BizTalk Server 内のクラスター化リソースとして、BizTalk ホストを構成できるようにする機能の提供、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター グループ。 ホスト クラスターのサポートは、BizTalk の統合の高可用性が、FTP 受信ハンドラーなどを実行するか複数のホスト インスタンスで同時に、アダプターを受信するにはサポートまたは特定の状況では、POP3 受信ハンドラーに提供されます。 MSMQ サービスのクラスター化が必要となるような状況でも、MSMQ アダプターによって送受信されたメッセージについて、トランザクションの一貫性を確実に保つことができます。  
  
> [!NOTE]
>  ホスト クラスタ リングは、BizTalk Server Enterprise Edition でのみ使用できます。  
> 
> [!NOTE]
>  BizTalk ホストをクラスターする前に構成した 2 つ以上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]のメンバーとして、BizTalk グループ内のコンピューターを[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスター。 構成の詳細については、[!INCLUDE[btsWinSvrNoVersion](../includes/btswinsvrnoversion-md.md)]クラスターを参照してください[Windows Server 2008 のクラスタ リング ドキュメント、ホワイト ペーパー、web キャスト、グループ](http://go.microsoft.com/fwlink/?LinkId=156818)(<http://go.microsoft.com/fwlink/?LinkId=156818>)。  
  
 BizTalk ホストのクラスター サポートを 5 つの統合 BizTalk アダプターの高可用性を実現する使用可能な: FTP アダプター、MSMQ アダプター、POP3 アダプター、SQL アダプター、および SAP アダプター。 また、順次配送の目的でアダプターの単一インスタンスを実行する場合に、ホスト クラスター サポートを利用して高い可用性を実現できます。  
  
 すべての BizTalk アダプター ハンドラーは、クラスター化されたホストで実行できますが、以下の説明に従って以外のクラスター化されたホストでアダプター ハンドラーの実行からの利点はありません。 以下のセクションで説明したシナリオのいずれかの処理要件場合は、クラスター化されたホストでアダプター ハンドラーを実行する必要があります。 設定の詳細な手順について[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]クラスターを参照してください[Improving Fault Tolerance in Windows Server 2008 フェールオーバー クラスターまたは Windows Server 2003 サーバー クラスターを使用して BizTalk Server](http://go.microsoft.com/fwlink/?LinkId=156819) (<http://go.microsoft.com/fwlink/?LinkId=156819>)。  
  
## <a name="scenarios-for-running-adapter-handlers-in-clustered-hosts"></a>クラスター化されたホストでアダプター ハンドラーを実行するためのシナリオ  
 、処理の要件が以下に示すシナリオのいずれかを含める場合は、クラスター化されたホストでアダプター ハンドラーを実行する必要があります。  
  
- クラスター化された BizTalk ホストで FTP アダプターの受信ハンドラーを実行する  
  
- クラスター化された BizTalk ホストで MSMQ アダプター ハンドラーを実行する  
  
- クラスター化された BizTalk ホストで POP3 アダプターの受信ハンドラーを実行する  
  
- クラスター化された BizTalk ホストで順次配送をサポートする受信アダプターを実行する  
  
  これらのシナリオの詳細については、次を参照してください。[されたクラスター化されたホストでアダプター ハンドラーの実行に関する考慮事項](http://go.microsoft.com/fwlink/?LinkId=151284)(http://go.microsoft.com/fwlink/?LinkId=151284)します。  
  
## <a name="see-also"></a>参照  
 [スケール アウト、受信ホスト](../technical-guides/scaling-out-receiving-hosts.md)   
 [スケール アウト処理ホスト](../technical-guides/scaling-out-processing-hosts.md)   
 [送信ホストのスケールアウト](../technical-guides/scaling-out-sending-hosts.md)