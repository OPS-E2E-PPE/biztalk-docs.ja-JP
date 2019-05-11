---
title: 無効な証明書が見つかりました |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1b3a9ae8-a9d7-4025-bacd-443e136ff980
caps.latest.revision: 22
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9194267eecdbf2247155df297dffeedbf2cac3a8
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65381360"
---
# <a name="invalid-certificate-found"></a>無効な証明書が見つかりました
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                             無効な証明書が見つかりました                              |
  
## <a name="explanation"></a>説明  
 WCF トランスポートの有効な証明書を提供しませんでした。  

#### <a name="user-action"></a>ユーザーの操作
証明書を追加します。 
  
## <a name="add-a-certificate"></a>証明書を追加します。  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブ。  
  
9. **[編集]** をクリックします。  
  
10. **Id エディター**  ダイアログ ボックスで、検索条件の確認、**証明書参照**有効な証明書を示すセクションが正しく構成されてです。  
  
    Wcf-custom と Wcf-customisolated アダプターでは、確実に検索条件、**証明書参照**証明書の有効な証明書を示すセクションが正しく構成されて**ストア名**.  
  
## <a name="add-a-certificate-for-standard-wcf-adapters"></a>標準の WCF アダプター用の証明書を追加します。  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブ。  
  
9. いることを確認、**拇印**サービスとクライアント証明書のプロパティは、証明書の有効な証明書を示す**ストア名**します。  
  
   証明書スナップインでは、WCF トランスポートのため、有効な証明書がインストールされていることを確認します。  
  
## <a name="see-also"></a>関連項目 
  
[WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)  