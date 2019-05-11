---
title: 構成をインポートできません |。Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2887da50-4f74-4259-a7d6-c87bc9b9fc58
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2dd4c5b2264c5f9ace89b206f2e948083a606b2
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292742"
---
# <a name="unable-to-import-configuration"></a>構成をインポートできません
## <a name="details"></a>詳細  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                         0                                          |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                                         0                                          |
|  メッセージ テキスト   |                   ファイルから構成をインポートできません"{0}"。                   |
  
## <a name="explanation"></a>説明  
 このエラーは複数の理由が考えられます。  
  
-   構成ファイルには、指定されたエンコードに無効な文字を含めることができます。  
  
-   ルート要素がない可能性があります。  
  
-   ルート レベルのデータは、有効でない可能性があります。  
  
> [!NOTE]
>  このような状況とユーザーの操作は、Wcf-custom および Wcf-customisolate アダプターにのみ適用されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 有効な構成ファイルをインポートするのにには、次の手順を使用します。  
  
#### <a name="to-import-a-valid-configuration-file"></a>有効な構成ファイルをインポートするには  
  
1. クリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理**します。  
  
2. コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開**アプリケーション**します。  
  
3. アプリケーションを見つけて、トランスポートを特定します。  
  
4. トランスポート名を右クリックします。  
  
5. **[プロパティ]** をクリックします。  
  
6. ポート**型**一覧で、適切なポートを選択します。  
  
7. をクリックして**構成**です。  
  
8. **WCF [**<em>トランスポートの種類</em>**] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**インポート/エクスポート**タブ。  
  
9. **[インポート]** をクリックします。 有効であり、完全な構成ファイルをインポートします。  
  
   サービス構成エディターで開くことによって、構成ファイルの有効性を確認することも **(開始 > すべてのプログラム > Windows SDK)** (この手順を前提とする Windows SDK をインストールします)。開いている**svcConfigEditor.exe**構成ファイルの各プロパティを確認します。