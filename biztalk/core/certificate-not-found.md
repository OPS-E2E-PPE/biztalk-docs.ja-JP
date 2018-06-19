---
title: 証明書が見つかりません |。Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 629b199f-1884-4e88-beaa-a2e5c5e792e9
caps.latest.revision: 24
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f1c18f112edc14375e6edc2aaa52c9e468d1bd39
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232610"
---
# <a name="certificate-not-found"></a>証明書が見つかりません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|証明書が見つかりません。|  
  
## <a name="explanation"></a>説明  
 指定した検索条件の証明書が見つかりませんでした。  

#### <a name="user-action"></a>ユーザーの操作
証明書の検索条件を確認します。 
  
## <a name="verify-search-criteria"></a>検索条件を確認します  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]** をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
9. **[編集]** をクリックします。  
  
10. **Id エディター**  ダイアログ ボックスで、ことを確認して内の検索条件、**証明書参照**セクションが有効な証明書を示すために正しく構成されてです。  
  
 Wcf-custom と Wcf-customisolated アダプターでは、確実に検索条件、**証明書参照**セクションでは、証明書の有効な証明書を示すために正しく構成されて**ストア名**.  
  
## <a name="verify-search-criteria-for-standard-wcf-adapters"></a>標準の WCF アダプタの検索条件を確認してください。  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]** をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。  
  
9. いることを確認、**拇印**サービスとクライアント証明書のプロパティが証明書ストアに有効な証明書を指定します。  
  
10. 証明書スナップインで、WCF トランスポート用の有効な証明書がインストールされていることを確認します。  

## <a name="see-also"></a>参照 
  
-   [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)  
  
