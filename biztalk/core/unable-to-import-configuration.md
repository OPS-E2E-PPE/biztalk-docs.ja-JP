---
title: 構成をインポートできません |。Microsoft ドキュメント
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
ms.openlocfilehash: 8e565b466e4f9ce8af3745948952b4318a029ff2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286682"
---
# <a name="unable-to-import-configuration"></a>構成をインポートできません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|構成をファイル "{0}" からインポートできません|  
  
## <a name="explanation"></a>説明  
 このエラーには複数の理由が考えられます。  
  
-   構成ファイルに、指定したエンコーディングでは無効な文字が含まれる可能性があります。  
  
-   ルート要素が欠落している可能性があります。  
  
-   ルート レベルのデータが無効な可能性があります。  
  
> [!NOTE]
>  この状況およびユーザー操作は、WCF-Custom アダプターおよび WCF-CustomIsolate アダプターのみに適用されます。  
  
## <a name="user-action"></a>ユーザーの操作  
 有効な構成ファイルをインポートするには、次の手順を実行します。  
  
#### <a name="to-import-a-valid-configuration-file"></a>有効な構成ファイルをインポートするには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]** をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**インポート/エクスポート**タブです。  
  
9. **[インポート]** をクリックします。 有効で完成した構成ファイルをインポートします。  
  
 サービス構成エディターで開くことによって、構成ファイルの有効性を確認することも **(開始 > すべてのプログラム > Windows SDK)** (この手順を想定 Windows SDK をインストールしてあります)。開いている**svcConfigEditor.exe**構成ファイルの各プロパティを確認してください。