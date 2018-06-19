---
title: ディスク、IP アドレスを使用してクラスター グループを作成し、名前を Resource1 する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b361f721-60db-485e-9ce3-48a6871ebd79
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 63310706742ffcc10de5266dda7053da79fc04fe
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249306"
---
# <a name="how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource"></a>ディスク、IP アドレス、および名前リソースを使用してクラスター グループを作成する方法
クラスター化された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントと依存関係に NetBIOS、クラスター化された経由でネットワーク経由でアクセスできる**ネットワーク名**同じクラスター グループにリソースを作成する必要があります。 TCP/IP プロトコル経由でアクセスできるようにクラスター化されたネットワーク名リソースの**IP アドレス**も同じクラスター グループにリソースを作成する必要があります。 いくつか[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]の依存関係も使用する必要はクラスター化された**物理ディスク**リソースを正常に機能します。 使用して、クラスター グループを作成する、**物理ディスク**、 **IP アドレス**と**ネットワーク名**リソースに次の手順します。  
  
### <a name="to-create-a-service-or-application-with-a-physical-disk-ip-address-and-network-name-resource"></a>物理ディスク、IP アドレス、およびネットワーク名リソースを使用してサービスまたはアプリケーションを作成するには  
  
1.  Windows では、をクリックして**開始**、**プログラム**、**管理ツール**、し**フェイル オーバー クラスター管理**フェールオーバーを開始するにはクラスター管理プログラムです。  
  
2.  フェールオーバー クラスター管理を実行しているクラスター ノードに、すべてのサービスとアプリケーションをフェールオーバーします。 サービスまたはアプリケーションがフェールオーバーするサービスまたはフェールオーバー クラスター管理の左側のウィンドウでアプリケーションを右クリックして、指す**このサービスまたはアプリケーションを別のノードに移動**をクリックして、移行先ノードを選択します。  
  
    > [!NOTE]
    >  実行中のクラスター リソースをホストしているクラスター ノードとも呼ばれます、 **active**ノード。 実行されていないクラスター リソースをホストしているクラスター ノードとも呼ばれます、**パッシブ**ノード。  
  
3.  左側のペインで右クリック**サービスとアプリケーション**、 をクリックして**サービスまたはアプリケーションを構成**、高可用性ウィザードを起動し、をクリックする**次**.  
  
4.  クリックして選択**ファイル サーバー**  をクリック**次**です。  
  
    > [!NOTE]
    >  選択すると**ファイル サーバー**ディスク リソースを持つクラスター グループを作成する簡単な方法としてこの時点で実行されます。  
  
5.  **クライアント アクセス ポイント**高可用性ウィザードのページに一意のネットワーク名を入力してください、**名前**ボックスで、たとえば*BizTalkCluster*、利用可能な IP を入力してくださいアドレス**アドレス**、順にクリック**次**です。  
  
6.  **[記憶域の**] ページで、クリックして、使用可能なディスク リソースを選択し、をクリックして**次**です。  
  
7.  **確認**ページをクリックして**次**クラスター グループを作成します。  
  
8.  **概要**ページをクリックして**完了**です。