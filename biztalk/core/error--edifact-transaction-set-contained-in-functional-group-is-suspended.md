---
title: "解析中にエラーが発生しました。 Edifact トランザクション セットの機能グループに含まれているが次のエラーで中断されています |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 986a7220-d35a-4047-8996-7d44c7d2b823
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 70428ae8f430ea5ccb9ff13e068716cb35555f69
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a>解析中にエラーが発生しました。 機能グループに含まれる EDIFACT トランザクション セットが次のエラーで中断されています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EfactTransactionSetReceiveError|  
|メッセージ テキスト|解析中にエラーが発生しました。 Edifact トランザクション セット id '{0}' id '{1}' の機能グループに含まれている次のエラーで送信者 id '{3}' と ' {2}'、id を持つインターチェンジの受信者 id '{4}' が中断されています。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、識別されたトランザクション セットで、示されたエラーが発生したため、EDI 受信パイプラインでグループの受信 EDIFACT インターチェンジを解析できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、ドキュメントで問題解決の方法を確認します。