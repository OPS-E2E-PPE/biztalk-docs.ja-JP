---
title: ディスク、IP アドレスを使用したクラスター グループを作成し、名前を Resource1 する方法 |Microsoft Docs
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
ms.openlocfilehash: 60b76da3fe031881eea3491469ac0f9d0bfe5c48
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65385593"
---
# <a name="how-to-create-a-cluster-group-with-a-disk-ip-address-and-name-resource"></a>ディスク、IP アドレス、および名前リソースをクラスター グループを作成する方法
クラスター化された[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]コンポーネントと依存関係に NetBIOS、クラスター化された経由でネットワーク経由でアクセスできる**ネットワーク名**同じクラスター グループにリソースを作成する必要があります。 TCP/IP プロトコル経由でアクセスできるクラスター化されたネットワーク名リソース、 **IP アドレス**も同じクラスター グループにリソースを作成する必要があります。 いくつか[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]依存関係をクラスター化を使用する必要も**物理ディスク**正常に機能するリソース。 使用してクラスター グループを作成する、**物理ディスク**、 **IP アドレス**と**ネットワーク名**リソースに次の手順します。  
  
### <a name="to-create-a-service-or-application-with-a-physical-disk-ip-address-and-network-name-resource"></a>物理ディスク、IP アドレス、およびネットワーク名リソースにサービスまたはアプリケーションを作成するには  
  
1.  Windows、 をクリックして**開始**、**プログラム**、**管理ツール**、し**フェールオーバー クラスター管理**フェールオーバーを開始するにはクラスター管理プログラム。  
  
2.  すべてのサービスとアプリケーションのフェールオーバー クラスター管理を実行しているクラスター ノードをフェールオーバーします。 サービスまたはアプリケーションをフェールオーバーするサービスまたはフェールオーバー クラスター管理の左側のウィンドウでアプリケーションを右クリックをポイントして**このサービスまたはアプリケーションを別のノードに移動**と宛先ノードを選択する をクリックします。  
  
    > [!NOTE]
    >  実行中のクラスター リソースをホストするクラスター ノードとも呼ばれますが、 **active**ノード。 実行されていないクラスター リソースをホストするクラスター ノードとも呼ばれますが、**パッシブ**ノード。  
  
3.  左側のウィンドウで右クリック**サービスとアプリケーション**、 をクリックして**サービスまたはアプリケーション構成**を高可用性ウィザードを起動し、順にクリックします**次**.  
  
4.  クリックして選択**ファイル サーバー**  をクリック**次**します。  
  
    > [!NOTE]
    >  選択**ファイル サーバー**ディスク リソースを持つクラスター グループを作成する簡単な方法としてこの時点で実行されます。  
  
5.  **クライアント アクセス ポイント**高可用性ウィザードのページに一意のネットワーク名を入力してください、**名前**ボックスで、たとえば*BizTalkCluster*、使用可能な ip アドレスを入力しますアドレス**アドレス**、順にクリックします**次**します。  
  
6.  **[記憶域の**] ページで、クリックして、使用可能なディスク リソースを選択し、クリックして**次**。  
  
7.  **確認**ページ クリック **[次へ]** クラスター グループを作成します。  
  
8.  **概要**ページ クリック**完了**。