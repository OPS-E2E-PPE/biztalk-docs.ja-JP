---
title: 解析中にエラーが発生しました。 次のエラーが発生しました、Edifact インターチェンジ、グループが含まれていませんでした |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d6b324fd-f365-41b9-81aa-b6c5c5d3f673
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 550e5ca207bef7fdcb42ffcbd52e114ad3dc95ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239586"
---
# <a name="error-encountered-during-parsing-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a>解析中にエラーが発生しました。 グループを含まない EDIFACT インターチェンジに、次のエラーがありました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EfactFunctionalGroupReceiveErrorWithoutGroup|  
|メッセージ テキスト|解析中にエラーが発生しました。 インターチェンジ id '{0}'、送信者 id '{1}' で、グループを含まない Edifact インターチェンジ受信者 id '{2}' には、次のエラーが必要があります。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、示されたエラーのため、グループを含まない受信 EDIFACT インターチェンジの解析中に、EDI 受信パイプラインでエラーが発生したことを示します。 EDIFACT インターチェンジでは、グループは省略可能です。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してエラーを特定し、製品のヘルプで問題解決の方法を確認してください。