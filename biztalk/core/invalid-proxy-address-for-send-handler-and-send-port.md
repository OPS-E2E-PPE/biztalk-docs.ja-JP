---
title: 無効なプロキシ アドレス (送信ハンドラーと送信ポート用) |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ccedd23e-7d44-4419-b519-e04511e1f176
caps.latest.revision: 21
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bdfa5951ed261d3e8bd63811764595d1b7e3858c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330619"
---
# <a name="invalid-proxy-address-for-send-handler-and-send-port"></a>(送信ハンドラーと送信ポート) 用の無効なプロキシ アドレス
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                             無効なプロキシ アドレス: {0}                             |
  
## <a name="explanation"></a>説明  
 WCF 送信ハンドラーまたは WCF 送信ポートが有効なプロキシ アドレスでは提供しませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 プロキシ アドレスを構成するのにには、次の手順を使用します。  
  
#### <a name="to-configure-a-proxy-address"></a>プロキシ アドレスを構成するには  
  
1. をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** 、 をクリック**BizTalk Server 管理コンソール**です。  
  
2. コンソール ルートで展開**BizTalk Server 管理**、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**プロキシ**タブ。  
  
9. いることを確認でプロキシ アドレス、**プロキシ設定**セクションが正しく構成されています。  
  
   送信ポートと送信ハンドラーの詳細については、次のリソースを参照してください。  
  
-   [Wcf-wshttp 送信ポートを構成する方法](../core/how-to-configure-a-wcf-wshttp-send-port.md)  
  
-   [Wcf-basichttp 送信ポートを構成する方法](http://msdn.microsoft.com/library/acdb50fa-57fe-4657-9561-b6b2f4919c7f)  
  
-   [Wcf-basichttp 送信ハンドラーを構成する方法](http://msdn.microsoft.com/library/18dcc616-4732-42f8-bd64-e55a5ebbaa49)  
  
-   [Wcf-wshttp 送信ハンドラーを構成する方法](../core/how-to-configure-a-wcf-wshttp-send-handler.md)  
  
-   [Wcf-custom 送信ポートを構成する方法](../core/how-to-configure-a-wcf-custom-send-port.md)