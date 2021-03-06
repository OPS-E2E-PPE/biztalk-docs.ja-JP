---
title: HTTP 送信ハンドラを構成する方法 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, HTTP adapters
- configuring [HTTP adapters], send handlers
- HTTP adapters, send handlers
ms.assetid: 821bf30c-b220-4ded-953d-7e745c0698b9
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53da31eba06cb5b53ca18e7ddacafc75dda5ed55
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65386413"
---
# <a name="how-to-configure-an-http-send-handler"></a>HTTP 送信ハンドラを構成する方法
HTTP 送信ハンドラが関連付けられているホストを変更するのにには、次の手順を使用します。  

> [!NOTE]
>  各ホストには、1 つだけ送信ハンドラーが関連付けられていることができます。  
> 
> [!CAUTION]
>  HTTP または SOAP アダプタ ハンドラを使用する場合は、Microsoft では、これらのハンドラーのホスト インスタンスをインストールすることをお勧め[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]、[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]コンピューター。  

### <a name="to-change-global-variables-for-an-http-send-handler"></a>グローバル変数を HTTP 送信ハンドラーを変更するには  

1. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**します。  

2. 展開したアダプターの一覧でクリックして**HTTP**では、右側のウィンドウは、構成する送信ハンドラーを右クリックし、**プロパティ**します。  

3. **アダプター ハンドラーのプロパティ** ダイアログ ボックスの 、**全般** タブで、**ホスト名**一覧で、送信ハンドラーが関連付けられているが、ホストを選択します。  

4. **プロパティ** タブで、次の操作を行います。  


   |         プロパティ          |                                                                                                                                                                                                 目的                                                                                                                                                                                                  |
   |---------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **Request timeout (sec)** | タイムアウトを秒単位で指定、サーバーからの応答を待機しているとき。<br /><br /> ゼロ (0) に設定すると、HTTP アダプター計算要求メッセージのサイズに基づいて、タイムアウトします。<br /><br /> 値を設定しないと、ハンドラの値が使用されます。<br /><br /> **既定値:** 0<br /><br /> **種類:** Long<br /><br /> **最小値:** 0<br /><br /> **最大値:** MAX_LONG です。 |
   |   **リダイレクトの最大数**   |                                                                                                       送信されるメッセージに許可されるリダイレクトの最大数を指定します。<br /><br /> **既定値:** 5<br /><br /> **種類:** Int<br /><br /> **最小値:** 0<br /><br /> **最大値:** 10                                                                                                       |
   |     **コンテンツの種類**      |                                                                 要求メッセージのコンテンツの種類を指定します。<br /><br /> 値を設定しないと、ハンドラの値が使用されます。<br /><br /> **既定値:** テキストまたは XML<br /><br /> **種類:** String<br /><br /> **最小長:** 0<br /><br /> **最大長:** 256                                                                  |


5. **プロキシ** タブで、次の操作を行います。  


   |   プロパティ    |                                                                                                                          目的                                                                                                                           |
   |---------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
   | **[プロキシを使用する]** |                                                                HTTP 送信ハンドラがプロキシ サーバーを使用するかどうかを指定します。<br /><br /> **既定値:** False<br /><br /> **種類:** ブール値                                                                |
   |  **[サーバー]**   |               この送信ポートのプロキシ サーバー アドレスを指定します。<br /><br /> このプロパティには、値がある場合**プロキシを使用して、** は**True**。<br /><br /> **種類:** String<br /><br /> **最小長:** 0<br /><br /> **最大長:** 256                |
   |   **[ポート]**    | この送信ポートのプロキシ サーバー ポートを指定します。<br /><br /> このプロパティには、値がある場合**プロキシを使用して、** は**True**。<br /><br /> **既定値:** 80<br /><br /> **種類:** Long<br /><br /> **最小値:** 0<br /><br /> **最大値:** 65535 |
   | **ユーザー名** |      プロキシ サーバーで認証に使用するユーザー名を指定します。<br /><br /> このプロパティには、値がある場合**プロキシを使用して、** は**True**。<br /><br /> **種類:** String<br /><br /> **最小長:** 0<br /><br /> **最大長:** 256       |
   | **Password**  |        プロキシ サーバーで認証に使用するユーザー パスワードを指定します。<br /><br /> このプロパティには、値がある場合**プロキシを使用して、** は**True**。<br /><br /> **種類:** String<br /><br /> **最小長:** 0<br /><br /> **最大長:** 256        |


6. **[OK]** をクリックします。  

## <a name="see-also"></a>参照  
 [HTTP アダプターの構成](../core/configuring-the-http-adapter.md)