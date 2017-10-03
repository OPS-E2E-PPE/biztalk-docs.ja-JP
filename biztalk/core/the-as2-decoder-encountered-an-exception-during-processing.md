---
title: "AS2 デコーダーの処理中に例外が発生しました |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b5f16d2e-e83c-4e2c-84be-41b5ed012dce
caps.latest.revision: "9"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2826a938a4f081b8c5895da809e9f16966e25834
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="the-as2-decoder-encountered-an-exception-during-processing"></a>AS2 デコーダーで、処理中に例外が発生しました
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|AS2 エンジン|  
|シンボル名|AS2DecoderExceptionEncounteredDuringProcessing|  
|メッセージ テキスト|AS2 デコーダで、処理中に例外が発生しました。  メッセージと例外の詳細については次のようには: AS2-から:"{0}"AS2-を:「\ 」MessageID:「\ {2 \}」MessageType:「{3}」例外:「\ {4\}」|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、AS2 デコーダーの問題のため、受信パイプラインが受信 AS2 メッセージを処理できなかったことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、AS2 エラー コードを確認してエラー状態の性質を特定します。 AS2 エラー コードの詳細については、[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] ヘルプ ファイルの「AS2 エラー コード」トピックを参照してください。