---
title: "解析中にエラーが発生しました。 Edifact 機能グループのインターチェンジに次のエラーが発生しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 77ca78b3-8a1f-4da5-9c15-524ab6802457
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6af00ae6500419fcb3ed687da89415e7594f1adc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="error-encountered-during-parsing-the-edifact-functional-group-in-interchange-had-the-following-errors"></a>解析中にエラーが発生しました。 インターチェンジ内の EDIFACT 機能グループに次のエラーがありました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EfactFunctionalGroupReceiveError|  
|メッセージ テキスト|解析中にエラーが発生しました。 Edifact 機能グループ id '{0}'、id '{1}' を持つインターチェンジの送信者 id '{2}' に受信者 id '{3}' では、次のエラーがありました。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、識別された機能グループに、示されたエラーがあったため、EDIFACT の受信インターチェンジを解析しているときに EDI 受信パイプラインでエラーが発生したことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してグループのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。