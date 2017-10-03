---
title: "クライアント証明書の拇印が指定されていないために必要な |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 19307bdb-29d7-4a79-9472-dda24dd8b263
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 17eb34655ab0acd379e493540f8cd0922e5d8be9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="required-client-certificate-thumbprint-not-specified"></a>必要なクライアント証明書の拇印が指定されていません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|必要なクライアント証明書の拇印が指定されていません。|  
  
## <a name="explanation"></a>説明  
 WCF 送信ポートのセキュリティ設定に必要なクライアント証明書のプロパティが設定されていませんでした。  
  
## <a name="user-action"></a>ユーザーの操作  
 WCF 送信ポートのセキュリティ設定を構成するには、次の手順を実行します。  
  
#### <a name="to-configure-security-settings"></a>セキュリティ設定を構成するには  
  
1.  をクリックして**開始**、 をクリックして**すべてのプログラム**、 をクリックして[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]、 をクリック**BizTalk Server 管理コンソール**です。  
  
2.  コンソール ルートで  [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、次にトランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  **[プロパティ]**をクリックします。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  をクリックして**構成**です。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、をクリックして、**セキュリティ**タブです。  
  
9. いることを確認、**クライアント証明書**プロパティを構成します。  
  
 証明書の詳細については、次の情報を参照してください。  
  
-   [WCF アダプターの証明書のインストール](../core/installing-certificates-for-the-wcf-adapters.md)