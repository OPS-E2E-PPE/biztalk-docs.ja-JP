---
title: 通信方式エラー |Microsoft ドキュメント
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 06656073-9bae-4d6f-98ae-2714a72ee79c
caps.latest.revision: 5
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 36677694b8f2d0973c04d942a196d055b696bd5c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
ms.locfileid: "22232210"
---
# <a name="communication-pattern-errors"></a>通信方式エラー
診断および WCF の通信方式エラーを解決するための情報です。  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a>エラー メッセージは一方向のポートではサポートされていません
  
||エラーの詳細|  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|0|  
|メッセージ テキスト|エラー メッセージは一方向のポートではサポートされていません。 サービス「{1}」説明"{0}"ポートの種類を修正し、ウィザードを再実行|  
  
## <a name="explanation"></a>説明  
 このエラーは、使用するサービスが一方向のサービスであり、誤って指定されたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 通信パターンを一方向から要求 - 応答に切り替える方法でサービスを修正します。 または、コードの誤りを削除します。
 
 