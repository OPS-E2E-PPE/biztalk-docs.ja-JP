---
title: "AS2 EDIINT MIC テーブルにエントリを作成できません |。Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a1c75d70-e39e-4465-b32b-db646c059c9b
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c51cac2861fabaf8fc50269623130c90f3d445b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-create-the-entry-in-the-as2-ediint-mic-table"></a>AS2 EDIINT MIC テーブルにエントリを作成できません
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|AS2MicDataStoreCreateEntryError|  
|メッセージ テキスト|AS2 EDIINT MIC テーブルにエントリを作成できません。 テーブルに挿入しようとしている AS2-From、AS2-To、および MessageID の組み合わせが重複している可能性があります。  エラー: {0}|  
  
## <a name="explanation"></a>説明  
 このエラーは、データベース接続に問題があるか、または行のキーが既にデータベース テーブルに存在していることを示します。 エラー メッセージの全文には、挿入操作が失敗した理由に関する情報が示されます。 テーブルのエントリは MDN の受信後に (成功または失敗にかかわらず) 削除されるので、このエラーが MDN の受信後に発生することはありません。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、挿入操作が発生した理由について、エラー メッセージの全文を確認します。 SQL の EDIINT_MIC テーブルで、AS2-From と AS2-To MessageID の重複した組み合わせがあるかどうかをチェックします。 ある場合は、削除します。