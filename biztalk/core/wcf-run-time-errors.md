---
title: "WCF の実行時エラー |Microsoft ドキュメント"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c5591bd4-aa15-4c7a-903e-fc73b880692f
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 97f4107ddf791b8d9fd152f2258cd3185f23498f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/20/2017
---
# <a name="wcf-run-time-errors"></a>WCF 実行時エラー
診断および解決する WCF の実行時イベントについて説明します。  
  
## <a name="wcf-service-host-restarted"></a>WCF サービス ホストが再起動されました
  
||エラーの詳細|  
|-|-|  
|製品名|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|製品バージョン|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|イベント ID|0x1FB0|  
|イベント ソース|0|  
|コンポーネント|0|  
|シンボル名|BTS_I_WCF_SERVICE_HOST_RESTARTED|  
|メッセージ テキスト|0|  
  
## <a name="explanation"></a>説明  
 このメッセージは、WCF アダプターが "参考" イベント ログ エントリを書き込む方法を示します (アダプター向けに用意された API では、情報ではなく警告またはエラーを作成できます)。  
  
## <a name="user-action"></a>ユーザーの操作  
 イベント ログにこの情報イベントが含まれている場合は、自動回復が正常に完了したことを示します。 このメッセージについてその他の操作は必要ありません。