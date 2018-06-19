---
title: シリアル化中にエラーが発生しました。 次のエラーが発生しました、Edifact インターチェンジ、グループが含まれていませんでした |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: af693139-e4cd-4bcb-922c-79caa148d3b7
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 72108104b359d4d06233cf9a623097bfd046a0ec
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22241762"
---
# <a name="error-encountered-during-serialization-the-edifact-interchange-which-did-not-contain-a-group-had-the-following-errors"></a>シリアル化中にエラーが発生しました。 グループを含まない EDIFACT インターチェンジに、次のエラーがありました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EfactFunctionalGroupSendErrorWithoutGroup|  
|メッセージ テキスト|シリアル化中にエラーが発生しました。 インターチェンジ id '{0}'、送信者 id '{1}' で、グループを含まない Edifact インターチェンジ受信者 id '{2}' には、次のエラーが必要があります。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、識別されたインターチェンジに、示されたエラーがあったため、EDIFACT の送信インターチェンジのシリアル中に EDI 送信パイプラインでエラーが発生したことを示します。 インターチェンジにグループは含まれないことに注意してください。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、エラー メッセージの情報を使用してインターチェンジのエラーを特定し、製品のヘルプで問題の解決方法を確認してください。