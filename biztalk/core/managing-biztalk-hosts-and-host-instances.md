---
title: "BizTalk ホストとホスト インスタンスを管理する |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- managing [hosts]
- hosts, managing
- managing [hosts], about managing hosts
ms.assetid: 7f329804-ca44-4799-8a5d-38b3146d8e5e
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0e60981f69bc3ff71bdd8581659f9cdd20f87467
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="managing-biztalk-hosts-and-host-instances"></a>BizTalk ホストとホスト インスタンスの管理
[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ホストとは、0 個以上の [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 実行時プロセスの論理的セットです。アダプター ハンドラー、受信場所 (パイプラインを含む)、オーケストレーションなどの各種アイテムをここに展開します。 ホストの詳細については、次を参照してください。[ホスト](../core/hosts.md)です。  
  
 ホスト インスタンスとは、メッセージの処理や送受信を行うプロセスです。 ホスト インスタンスは、1 つ以上のホストがマップされており、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] を稼働する各サーバーにインストールします。 ホスト インスタンスの詳細については、次を参照してください。[ホスト インスタンス](../core/host-instances.md)です。  
  
 ホストの特性は、次のとおりです。  
  
-   ホストは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オブジェクトの論理的なコンテナーです。  
  
-   特定のホストのインスタンスは各サーバーに 1 つのみです。  
  
-   1 つのホストを複数のサーバーにマップできます。  
  
 ホスト インスタンスの特性は、次のとおりです。  
  
-   ホスト インスタンスは、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] オブジェクトの物理的なコンテナーです。  
  
-   サーバーをホストにマップするときに、ホスト インスタンスを作成します。  
  
-   負荷分散目的で、またはフェールオーバー用に、さまざまなホストの複数のホスト インスタンスを 1 台のサーバーに配置できます。  
  
 次の図に、サーバー、ホスト、およびホスト インスタンスの関係を示します。  
  
 ![ホスト、ホスト インスタンス、およびサーバーの関係](../core/media/ebiz-ops-adm01.gif "ebiz_ops_adm01")  
ホスト、ホスト インスタンス、およびサーバー間のリレーションシップ  
  
## <a name="in-this-section"></a>このセクションの内容  
  
-   [BizTalk Server のホスティング環境を作成する方法](../core/how-to-create-a-biztalk-server-hosting-environment.md)  
  
-   [新しいホストを作成する方法](../core/how-to-create-a-new-host.md)  
  
-   [ホストのプロパティを変更する方法](../core/how-to-modify-host-properties.md)  
  
-   [ホストを削除する方法](../core/how-to-delete-a-host.md)  
  
-   [ホスト インスタンスを追加する方法](../core/how-to-add-a-host-instance.md)  
  
-   [ホスト インスタンスを起動する方法](../core/how-to-start-a-host-instance.md)  
  
-   [ホスト インスタンスを停止する方法](../core/how-to-stop-a-host-instance.md)  
  
-   [ホスト インスタンスを削除する方法](../core/how-to-delete-a-host-instance.md)  
  
-   [ホスト インスタンスのプロパティを変更する方法](../core/how-to-modify-host-instance-properties.md)