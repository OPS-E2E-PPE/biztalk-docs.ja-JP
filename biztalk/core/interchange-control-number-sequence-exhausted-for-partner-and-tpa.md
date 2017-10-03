---
title: "パートナーと TPA のインターチェンジの制御番号シーケンスが終了 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e77c0574-bc51-4690-a7f6-5702f6486f05
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b4744a8db00985db3e85c1cb8843f07b3488544b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="interchange-control-number-sequence-exhausted-for-partner-and-tpa"></a>パートナーと TPA のインターチェンジ制御番号のシーケンスが終了しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|EdiControlNumberExhaustedForParty|  
|メッセージ テキスト|TPA '{2}' のパートナー '{1}' を終了してインターチェンジ制御番号のシーケンス。 {2} - BizTalk Server 管理コンソールを使用して EDI プロパティでシーケンスをリセットします。|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、BizTalk Server で {2} でアグリーメントのインターチェンジ制御の範囲が使い果たされたため、ドキュメントを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するのには、チェックを {2} アグリーメントの制御番号をリセットまたは制御番号の範囲を増やすか、アグリーメントでは、制御番号範囲指定に対するリセット ボタンをクリックします。