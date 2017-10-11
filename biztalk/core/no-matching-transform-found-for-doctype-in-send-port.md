---
title: "一致する変換では見つかりませんでした DocType の送信ポート |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 23f62ac7-3849-49fe-a765-2be72880a4c9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8bc45ac0edf425bc19ab526fac6b2690f3a6b6d0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="no-matching-transform-found-for-doctype-in-send-port"></a>送信ポートに DocType と一致する変換が見つかりません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|NoMatchingTransformFoundForSendPortAndDocType|  
|メッセージ テキスト|一致する変換は送信ポート {1} 内の DocType {0} が見つかりません。 ExplorerOM の情報と一貫性がありません。|  
  
## <a name="explanation"></a>説明  
 このエラーは、指定された DocType および SendPort に一致する変換が見つからなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次の手順します。  
  
1.  BizTalk 管理コンソールを開き、変換を探してトランスポート名を右クリックします。  
  
2.  **[プロパティ]**をクリックします。  
  
3.  ポートの [種類] の一覧で、正しいポートを選択します。 をクリックして**構成**です。  
  
4.  [ポート名] 送信ポートのプロパティ ダイアログ ボックスでをクリックして**送信マップ**左側のウィンドウでします。  
  
5.  マップがここに表示されており、正しいドキュメントの種類に対応していることを確認します。