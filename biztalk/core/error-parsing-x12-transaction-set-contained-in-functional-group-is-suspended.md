---
title: "解析中にエラーが発生しました。 トランザクション機能グループに含まれているセットは、次のエラーで中断されていますが、X12 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 51c6fa8e-d81c-4ccb-93b4-852ab184c4e9
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6aa837fb86b34cfdd696874dd02ba26635bf7356
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-x12-transaction-set-contained-in-functional-group-is-being-suspended-with-following-errors"></a>解析中にエラーが発生しました。 機能グループに含まれる X12 トランザクション セットが次のエラーで中断されています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12TransactionSetReceiveError|  
|メッセージ テキスト|解析中にエラーが発生しました。 含まれるトランザクション セット id '{0}' の X12 機能グループ id '{1}'、id '{2}' のインターチェンジの送信者 id '{3}'、受信者 id '{4}' でが次のエラーで中断されています。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、識別されたトランザクション セットに、示されたエラーがあったため、受信 X12 インターチェンジの解析中に EDI 受信パイプラインでエラーが発生したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。