---
title: "アクション エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 87cf0a5b-d1dd-4807-9660-e8a8b7012b40
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 49f25f1f15307077943ef370a335885690bea22c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="action-errors"></a>アクション エラー
ここでは、WCF のアクション エラーを診断および解決するための詳細について説明します。  
  
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|単一のアクションに改行文字を含めることはできません。 改行文字をすべて削除するか、 アクション マッピングの構文を使用して複数のアクションを指定してください。|  
  
## <a name="explanation"></a>説明  
 このエラーは、送信ポートのアクション プロパティに、使用できない改行文字が含まれていることを示します。  
  
> [!NOTE]
>  この制限は、マッピングとしてアクションを定義するときには適用されません。  
  
## <a name="user-action"></a>ユーザーの操作  
 アクション プロパティを修正するには、次の手順を実行します。  
  
 
1.  開いている**BizTalk Server 管理**です。  
  
2.  コンソール ルートで  **BizTalk Server 管理コンソール**、展開**BizTalk グループ**、展開と**アプリケーション**です。  
  
3.  アプリケーションを特定し、トランスポートを特定します。  
  
4.  トランスポート名を右クリックします。  
  
5.  選択**プロパティ**です。  
  
6.  ポート**型**一覧で、適切なポートを選択します。  
  
7.  **[構成]**を選択します。  
  
8.  **WCF [***トランスポートの種類***] トランスポートのプロパティ**ダイアログ ボックスで、**全般**タブです。  
  
9. **SOAP アクション ヘッダー**セクションから改行文字を削除、**アクション**テキスト ボックス。  

## <a name="more-good-info"></a>詳細な情報  
 アクションの詳細については、次を参照してください[WCF 送信アダプタ用の SOAP アクションの指定。](../core/specifying-soap-actions-for-wcf-send-adapters.md)