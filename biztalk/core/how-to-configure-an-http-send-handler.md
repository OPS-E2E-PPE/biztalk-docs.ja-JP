---
title: "HTTP 送信ハンドラを構成する方法 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send handlers, HTTP adapters
- configuring [HTTP adapters], send handlers
- HTTP adapters, send handlers
ms.assetid: 821bf30c-b220-4ded-953d-7e745c0698b9
caps.latest.revision: "16"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7c63d9a6035ccb9c9c309f43dba9ba0a45bec547
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-configure-an-http-send-handler"></a>HTTP 送信ハンドラを構成する方法
次の手順を実行して、HTTP 送信ハンドラに関連付けられているホストを変更します。  
  
> [!NOTE]
>  各ホストに関連付けられる送信ハンドラーは 1 つだけです。  
  
> [!CAUTION]
>  HTTP アダプター ハンドラーまたは SOAP アダプター ハンドラーを使用するときは、これらのハンドラーのホスト インスタンスを Microsoft [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] コンピューターにインストールすることをお勧めします。  
  
### <a name="to-change-global-variables-for-an-http-send-handler"></a>HTTP 送信ハンドラのグローバル変数を変更するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**です。  
  
2.  展開したアダプターの一覧でクリックして**HTTP**をクリックして、右側のウィンドウは、構成する送信ハンドラを右クリック**プロパティ**です。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、送信ハンドラーが関連付けられる、ホストを選択します。  
  
4.  **プロパティ** タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**要求のタイムアウト (秒)**|サーバーからの応答を待機する際のタイムアウト時間を秒単位で指定します。<br /><br /> ゼロ (0) に設定すると、タイムアウト値は要求メッセージのサイズを基準に HTTP アダプタによって計算されます。<br /><br /> 値を設定しないと、ハンドラの値が使用されます。<br /><br /> **既定値:** 0<br /><br /> **型:**長<br /><br /> **最小値:** 0<br /><br /> **最大値:** MAX_LONG|  
    |**リダイレクトの最大数**|送信されるメッセージに許可されるリダイレクトの最大数を指定します。<br /><br /> **既定値:** 5<br /><br /> **型:** Int<br /><br /> **最小値:** 0<br /><br /> **最大値:** 10|  
    |**コンテンツの種類**|要求メッセージのコンテンツの種類を指定します。<br /><br /> 値を設定しないと、ハンドラの値が使用されます。<br /><br /> **既定値:** TEXT/XML<br /><br /> **型:**文字列<br /><br /> **最小の長さ:** 0<br /><br /> **最大長:** 256|  
  
5.  **プロキシ** タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**[プロキシを使用する]**|HTTP 送信ハンドラがプロキシ サーバーを使用するかどうかを指定します。<br /><br /> **既定値:** False<br /><br /> **型:**ブール|  
    |**[サーバー]**|この送信ポートのプロキシ サーバー アドレスを指定します。<br /><br /> 場合、このプロパティが値を必要と**プロキシを使用して**は**True**です。<br /><br /> **型:**文字列<br /><br /> **最小の長さ:** 0<br /><br /> **最大長:** 256|  
    |**[ポート]**|この送信ポートのプロキシ サーバー ポートを指定します。<br /><br /> 場合、このプロパティが値を必要と**プロキシを使用して**は**True**です。<br /><br /> **既定値:** 80<br /><br /> **型:**長<br /><br /> **最小値:** 0<br /><br /> **最大値:** 65535|  
    |**ユーザー名**|プロキシ サーバーで認証に使用するユーザー名を指定します。<br /><br /> 場合、このプロパティが値を必要と**プロキシを使用して**は**True**です。<br /><br /> **型:**文字列<br /><br /> **最小の長さ:** 0<br /><br /> **最大長:** 256|  
    |**Password**|プロキシ サーバーで認証に使用するユーザー パスワードを指定します。<br /><br /> 場合、このプロパティが値を必要と**プロキシを使用して**は**True**です。<br /><br /> **型:**文字列<br /><br /> **最小の長さ:** 0<br /><br /> **最大長:** 256|  
  
6.  **[OK]**をクリックします。  
  
## <a name="see-also"></a>参照  
 [HTTP アダプタの構成](../core/configuring-the-http-adapter.md)