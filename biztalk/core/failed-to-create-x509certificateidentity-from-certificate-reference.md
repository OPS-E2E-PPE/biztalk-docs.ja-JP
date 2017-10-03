---
title: "証明書参照から X509CertificateIdentity を作成できませんでした |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a3acee8e-c035-4e58-8bfc-397885b4d185
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c6bb03698010d667b27334f17fa7270de845c68
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="failed-to-create-x509certificateidentity-from-certificate-reference"></a>証明書参照から X509CertificateIdentity を作成できませんでした
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|証明書参照から X509CertificateIdentity を作成できませんでした。 (StoreName = {0}、StoreLocation = \  X509FindType = \ {2 \}、FindValue ="\ {3\}")|  
  
## <a name="explanation"></a>説明  
 このエラーは、アダプターで、エンドポイント ID 構成に指定されている X509Certificate の作成に失敗したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 証明書参照設定を確認するには、次の手順を実行します。  
  
#### <a name="to-configure-the-certificate-reference-settings"></a>証明書参照設定を構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**全般**タブです。  
  
9. **エンドポイント Id**セクションで、**を編集します。**  
  
10. **Id エディター**  ダイアログ ボックスで、いることを確認、**証明書参照**設定が有効です。