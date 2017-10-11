---
title: "無効なプロキシ アドレス (送信ハンドラーと送信ポート) |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ccedd23e-7d44-4419-b519-e04511e1f176
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d33af2f4fa068294c38ecb4146cd1f8d05d68aea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-proxy-address-for-send-handler-and-send-port"></a>無効なプロキシ アドレス (送信ハンドラーおよび送信ポート)
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|無効なプロキシ アドレス: {0}|  
  
## <a name="explanation"></a>説明  
 WCF 送信ハンドラーまたは WCF 送信ポートが、有効なプロキシ アドレスで指定されていませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 プロキシ アドレスを構成するには、次の手順を実行します。  
  
#### <a name="to-configure-a-proxy-address"></a>プロキシ アドレスを構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**プロキシ**タブです。  
  
9. いることを確認のプロキシ アドレス、**プロキシ設定**セクションが正しく構成されています。  
  
 送信ポートと送信ハンドラーの詳細については、次の情報を参照してください。  
  
-   [Wcf-wshttp 送信ポートを構成する方法](../core/how-to-configure-a-wcf-wshttp-send-port.md)  
  
-   [Wcf-basichttp 送信ポートを構成する方法](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)  
  
-   [Wcf-basichttp 送信ハンドラーを構成する方法](http://msdn.microsoft.com/library/18dcc616-4732-42f8-bd64-e55a5ebbaa49)  
  
-   [Wcf-wshttp 送信ハンドラーを構成する方法](../core/how-to-configure-a-wcf-wshttp-send-handler.md)  
  
-   [Wcf-custom 送信ポートを構成する方法](../core/how-to-configure-a-wcf-custom-send-port.md)