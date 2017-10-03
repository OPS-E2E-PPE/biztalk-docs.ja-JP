---
title: "シリアル化中にエラーが発生しました。 X12 機能グループが、次のエラーがありました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: dad987c3-92f3-4a6b-ba1a-b60f6ea2fbe4
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 27c6b74d713f0d182a07cc6a509cd7d06fc34b82
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-serialization-the-x12-functional-group-had-the-following-errors"></a>シリアル化中にエラーが発生しました。 X12 機能グループに次のエラーがありました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12FunctionalGroupSendError|  
|メッセージ テキスト|シリアル化中にエラーが発生しました。 受信者 id '{0}'、id '{1}' を持つインターチェンジの送信者 id '{2}' の X12 機能グループ id '{3}' 次のエラーが発生しました。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、識別された機能グループに、示されたエラーがあったため、X12 の送信インターチェンジのシリアル化中に EDI 送信パイプラインでエラーが発生したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用して機能グループのエラーを特定し、製品のヘルプで問題解決の方法を確認してください。