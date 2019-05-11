---
title: 送信 XML テンプレートが無効な |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f29bb60-8c04-4921-84bf-c629540a1c83
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b0978c88e1392c506970b11bac9774c1f48eb5a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330766"
---
# <a name="invalid-outbound-xml-template"></a>送信 XML テンプレートが無効です
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                           送信 XML テンプレートが無効です                            |
  
## <a name="explanation"></a>説明  
 複数の理由が考えられます。 送信 WCF メッセージ本文のテンプレートは、有効な XML をできない可能性があります。 指定されたエンコードに無効な文字に含めることができます。 ルート要素がない可能性があります。 ルート レベルのデータは、有効でない可能性があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 テンプレート式に有効な XML コードがあることを確認します。 無効な文字が含まれていないことと、1 つだけのルート要素があることを確認してください。  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**メッセージ**タブ。  
  
9. **送信 WCF メッセージ本文**セクションで、**テンプレート--テンプレートで指定されたコンテンツ**します。  
  
10. **XML**テキスト ボックスに、XML コードが有効であることを確認します。  
  
    テンプレートの詳細については、の次のリソースを参照してください、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]ヘルプします。  
  
-   [WCF アダプターのメッセージ本文の指定](../core/specifying-the-message-body-for-the-wcf-adapters.md)