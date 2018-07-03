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
ms.openlocfilehash: b8893bcd043ca046c310ee52276eb28476be4ea9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001179"
---
# <a name="using-windows-server-cluster-to-provide-high-availability-for-biztalk-server-hosts2"></a>Windows Server クラスターを使用して BizTalk Server Hosts2 の高可用性を実現するには
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows Server フェールオーバー クラスター グループ内のクラスター化リソースとして BizTalk ホストを構成するための機能を提供します。 ホストのクラスター化対応により、FTP の受信ハンドラー、(場合によっては) POP3 受信ハンドラーなど、本来であれば複数のホスト インスタンスで同時に実行することのできない、統合された BizTalk アダプターで高い可用性を実現できるようになっています。 MSMQ サービスのクラスター化が必要となるような状況でも、MSMQ アダプターによって送受信されたメッセージについて、トランザクションの一貫性を確実に保つことができます。  
  
> [!NOTE]
>  ホスト クラスタリングは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Enterprise Edition のみで使用できます。  
> 
> [!NOTE]
>  BizTalk ホストをクラスター化することができます、前に構成した 2 つ以上[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]内のコンピューター、 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Windows Server フェールオーバー クラスターのメンバーとしてグループ化します。 Windows Server フェールオーバー クラスターを構成する方法の詳細については、Windows Server のオンライン ヘルプを参照してください。  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server を Windows Server クラスターにインストールする際の考慮事項](../core/considerations-for-installing-biztalk-server-on-a-windows-server-cluster2.md)  
  
-   [BizTalk ホストをクラスター リソースとして構成する方法](../core/how-to-configure-a-biztalk-host-as-a-cluster-resource1.md)  
  
-   [クラスター化されたホストでのアダプター ハンドラーの実行に関する注意点](../core/considerations-for-running-adapter-handlers-within-a-clustered-host1.md)