---
title: "存在しないか無効なトランザクション セット制御番号 |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6064b974-e8cd-4486-abc2-010afe0d956e
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e9448c9be2cd05c7f7d8c18c13730933c1b5824
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="missing-or-invalid-transaction-set-control-number"></a>トランザクション セット制御番号が見つからないか無効です
## <a name="details"></a>詳細  
  
|||  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|イベント ID|-|  
|イベント ソース|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|コンポーネント|EDI エンジン|  
|シンボル名|X12TsMissingOrInvalidTsControlNumberDescription|  
|メッセージ テキスト|トランザクション セット制御番号が見つからないか無効です|  
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、トランザクション セット制御番号 (ST02 フィールド) が見つからないか無効な値であったため、受信または送信パイプラインでインターチェンジを処理できなかったことを示します。 トランザクション セット制御番号は英数字である必要があります。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、次のいずれかの操作を行います。  
  
1.  各トランザクション セットにトランザクション セット制御番号があることを確認します。  
  
2.  各トランザクション セット制御番号が英数字であることを確認します。