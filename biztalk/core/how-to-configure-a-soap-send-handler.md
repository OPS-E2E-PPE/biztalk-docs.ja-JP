---
title: SOAP 送信ハンドラーを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- send handlers, SOAP adapters
- SOAP adapters, denial of service
- denital of service, HTTP adapters
- configuring [SOAP adapters], send handlers
- configuring [SOAP adapters], denial of service
- SOAP adapters, send handlers
- denial of service, SOAP adapters
ms.assetid: fd610a3f-ca10-42e0-b81e-219e07e33830
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 65ca116b47e36d754b27839a09225aeb313c9e0f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248242"
---
# <a name="how-to-configure-a-soap-send-handler"></a>SOAP 送信ハンドラーを構成する方法
次の手順を実行して、SOAP 送信ハンドラーを構成します。  
  
> [!CAUTION]
>  HTTP または SOAP アダプタ ハンドラを使用する場合は、Microsoft では、これらのハンドラのホスト インスタンスをインストールすることをお勧め[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]または[!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)]コンピューター。  
  
### <a name="to-change-global-variables-for-a-soap-send-handler"></a>SOAP 送信ハンドラーのグローバル変数を変更するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、 [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**です。  
  
2.  展開したアダプターの一覧でクリックして**SOAP**、右側のペインで、構成する送信ハンドラを右クリックしをクリック**プロパティ**です。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、受信ハンドラーが関連付けられる、ホストを選択します。  
  
4.  **プロキシ** タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**[プロキシを使用する]**|SOAP 送信ハンドラーがプロキシ サーバーを使用するかどうかを示します。|  
    |**[サーバー]**|プロキシ サーバーの名前を指定します。<br /><br /> 場合にこのプロパティが値にのみ必要と**プロキシを使用して**が選択されています。<br /><br /> 型:文字列<br /><br /> 最小長: 0<br /><br /> 最大長: 256|  
    |**[ポート]**|SOAP 送信ハンドラーが使用するポートを指定します。<br /><br /> 場合にこのプロパティが値にのみ必要と**プロキシを使用して**が選択されています。<br /><br /> 既定値: 80<br /><br /> 型: 長整数<br /><br /> 最小値: 0<br /><br /> 最大値: 65535|  
    |**ユーザー名**|認証に使用するユーザー名を指定します。<br /><br /> 場合にこのプロパティが値にのみ必要と**プロキシを使用して**が選択されています。<br /><br /> 型:文字列<br /><br /> 最小長: 0<br /><br /> 最大長: 256|  
    |**Password**|認証に使用するパスワードを指定します。<br /><br /> 場合にこのプロパティが値にのみ必要と**プロキシを使用して**が選択されています。<br /><br /> 型:文字列<br /><br /> 最小長: 0<br /><br /> 最大長: 256|  
  
5.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [SOAP アダプターの構成](../core/configuring-the-soap-adapter.md)   
 [Web サービスの公開](../core/publishing-web-services.md)