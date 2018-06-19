---
title: Wcf-wshttp 送信ハンドラーを構成する方法 |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- WCF-WSHttp adapters, global variables
- configuring [WCF-WSHttp adapters], send handlers
- configuring [WCF-WSHttp adapters], global variables
- send handlers, WCF-WSHttp adapters
ms.assetid: b2c30edb-8f7b-4d3c-812b-5b877c47fda1
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 11566bcc902ccbda33b6b15922292390df3d5201
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248458"
---
# <a name="how-to-configure-a-wcf-wshttp-send-handler"></a>WCF-WSHttp 送信ハンドラーを構成する方法
WCF-WSHttp 送信ハンドラーを構成するには、次の手順に従います。  
  
> [!CAUTION]
>  WCF-WSHttp アダプター ハンドラーを使用する場合、これらのハンドラーのホスト インスタンスを [!INCLUDE[btsWinSvr2k8R2](../includes/btswinsvr2k8r2-md.md)] または [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)] コンピューターにインストールすることをお勧めします。  
  
### <a name="to-change-global-variables-for-a-wcf-wshttp-send-handler"></a>WCF-WSHttp 送信ハンドラーのグローバル変数を変更するには  
  
1.  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理コンソールで、展開[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**、展開**BizTalk グループ**、展開**プラットフォームの設定**、順に展開**アダプター**です。  
  
2.  展開したアダプターの一覧でクリックして**Wcf-wshttp**、右側のペインで、構成する送信ハンドラを右クリックしをクリック**プロパティ**です。  
  
3.  **アダプター ハンドラーのプロパティ** ダイアログ ボックスで、**全般** タブの 、**ホスト名**一覧で、受信ハンドラーが関連付けられる、ホストを選択します。  
  
4.  **全般** タブをクリックして**プロパティ**の**プロキシ** タブで、次の操作を行います。  
  
    |プロパティ|目的|  
    |--------------|----------------|  
    |**[プロキシを使用する]**|この送信ポートがプロキシ サーバーを使用するかどうかを示します。<br /><br /> 既定値はオフです。|  
    |**Address**|プロキシ サーバーのアドレスを指定します。 使用して、 **https**または**http**セキュリティ構成に応じてスキームです。 このアドレスの後に、コロンとポート番号を指定します。 たとえば、http://127.0.0.1:8080 と指定します。<br /><br /> このプロパティには、値の場合にのみが必要です。**プロキシを使用して**が選択されています。<br /><br /> 型:文字列<br /><br /> 最大長: 256<br /><br /> 既定値は空の文字列です。|  
    |**ユーザー名**|認証に使用するユーザー名を指定します。 統合認証または基本認証が使用されている場合は、"ドメイン\ユーザー名" のように、ユーザー名にドメインを含めます。 ダイジェスト認証を使用する場合、ユーザー名がドメインを含まない\\です。<br /><br /> このプロパティには、値の場合にのみが必要です。**プロキシを使用して**が選択されています。<br /><br /> 型:文字列<br /><br /> 最小長: 0<br /><br /> 最大長: 256<br /><br /> 既定値は空の文字列です。|  
    |**Password**|認証に使用するパスワードを指定します。<br /><br /> このプロパティには、値の場合にのみが必要です。**プロキシを使用して**が選択されています。<br /><br /> 型:文字列<br /><br /> 最小長: 0<br /><br /> 最大長: 256<br /><br /> 既定値は空の文字列です。|  
  
5.  **[OK]** をクリックします。  
  
## <a name="see-also"></a>参照  
 [Wcf-wshttp アダプタを構成します。](../core/configuring-the-wcf-wshttp-adapter.md)