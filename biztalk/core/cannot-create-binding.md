---
title: "バインディングを作成することはできません |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fbe1bd54-6031-4f90-a445-c1647b382a1a
caps.latest.revision: "20"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 227addce4f5a5c1d6d18b7e21646e5276732a28f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="cannot-create-binding"></a>バインドを作成できません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|バインドの種類が指定されていないため、バインドを作成できません。 "basicHttpBinding"、"wsHttpBinding"、または "customBinding" のようなバインドの種類を指定してください。|  
  
## <a name="explanation"></a>説明  
 WCF-Custom または WCF-CustomIsolated トランスポートを構成した後に、BindingType プロパティが設定されませんでした。 または、他のコード パスに問題がある可能性があります。 バインド設定のユーザー インターフェイスで値を指定する必要があります。 構成を見直し、受信場所のプロパティ領域のドロップダウン リストからバインドの種類を選択したことを確認します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、WCF-Custom または WCF-CustomIsolated トランスポートを構成するコードを見直します。 いることを確認、 **BindingType**用の XML データ内のプロパティ、 **TransportTypeData** ITransportInfo インターフェイスのプロパティが適切に設定します。  
  
 また、ようにバインドの種類を指定**basicHttpBinding**、 **wsHttpBinding**、または**customBinding**です。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**バインド**タブです。  
  
9. 値が指定されていることを確認、**バインディングの種類** ボックスの一覧です。  
  
 バインド構成の詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプで次の情報を参照してください。  
  
-   [Wcf-customisolated 受信場所を構成する方法](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [Wcf-custom 受信場所を構成する方法](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [Wcf-custom 送信ポートを構成する方法](../core/how-to-configure-a-wcf-custom-send-port.md)