---
title: 解析中にエラーが発生しました。 Edifact トランザクション セット (グループなしの) インターチェンジに含まれるが次のエラーで中断されています |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 901fef68-4649-480a-997c-b061d7d069d6
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2dc5633917c708f457f11fc824997fa7eb6d4c59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22240234"
---
# <a name="error-encountered-during-parsing-the-edifact-transaction-set-contained-in-interchange-without-group-is-being-suspended-with-following-errors"></a>解析中にエラーが発生しました。 インターチェンジに含まれる EDIFACT トランザクション セット (グループ以外) が、次のエラーで中断されています
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EfactTransactionSetReceiveErrorWithoutGroup|  
|メッセージ テキスト|解析中にエラーが発生しました。 Edifact トランザクション セット id '{0}' id '{1}'、送信者 id '{2}' を持つ (グループなしの) インターチェンジに含まれている受信者 id '{3}' で中断されていますが次のエラー。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、インターチェンジで識別されたトランザクション セットで、示されたエラーが発生したため、受信 EDIFACT インターチェンジ (グループ以外) の解析時に EDI 受信パイプラインでエラーが発生したことを示します。 このトランザクション セットは、インターチェンジ内のグループには含まれないことに注意してください。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してトランザクション セットのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。