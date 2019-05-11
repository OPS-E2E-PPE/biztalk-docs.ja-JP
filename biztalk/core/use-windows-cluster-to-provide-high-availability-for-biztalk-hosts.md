---
title: Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現する |Microsoft Docs
ms.custom: ''
ms.date: 2016-01-04
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Passive configuration [Master Secret server]
- Active configuration [Master Secret server]
- clustering, about clustering
- high availability
- Windows Server cluster, warnings
- installation, high availibility planning
- Master Secret server
- installation, configuring
- Master Secret server, configuring
- installation, Windows Server cluster
- clustering
ms.assetid: 4d7f0842-561e-49e0-ab08-504256b9294f
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6b6c4adaf94d71841beea4d5b7e306958881cca9
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65399963"
---
# <a name="using-windows-server-cluster-to-provide-high-availability-for-biztalk-server-hosts2"></a>Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows Server フェールオーバー クラスター グループ内のクラスター化リソースとして BizTalk ホストを構成するための機能を提供します。 ホスト クラスターのサポートは、BizTalk の統合の高可用性をサポートするためにアダプターを実行するか複数のホスト インスタンスで同時に、FTP などの受信ハンドラー、または特定の状況では、POP3 受信ハンドラーに提供されます。 MSMQ サービスのクラスター化が必要となるような状況でも、MSMQ アダプターによって送受信されたメッセージについて、トランザクションの一貫性を確実に保つことができます。  
  
> [!NOTE]
>  使用可能なホストのクラスタ リングは[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Enterprise Edition。  
> 
> [!NOTE]
>  BizTalk ホストをクラスター化することができます、前に構成した 2 つ以上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内のコンピューター、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows Server フェールオーバー クラスターのメンバーとしてグループ化します。 Windows Server フェールオーバー クラスターを構成する方法の詳細については、Windows Server のオンライン ヘルプを参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server を Windows Server クラスターにインストールする際の考慮事項](../core/considerations-for-installing-biztalk-server-on-a-windows-server-cluster2.md)  
  
-   [BizTalk ホストをクラスター リソースとして構成する方法](../core/how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)  
  
-   [クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)