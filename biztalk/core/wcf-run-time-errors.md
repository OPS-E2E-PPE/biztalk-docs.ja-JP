---
title: WCF 実行時エラー |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5591bd4-aa15-4c7a-903e-fc73b880692f
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8ca38035582fe8a8d37d66f61fbca820dd14c0c4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65266997"
---
# <a name="wcf-run-time-errors"></a>WCF 実行時エラー
診断および WCF の実行時イベントを解決するための情報です。  
  
## <a name="wcf-service-host-restarted"></a>WCF サービス ホストが再起動されました
  
|                 |                                   エラーの詳細                                    |
|-----------------|------------------------------------------------------------------------------------|
|  製品名   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| 製品バージョン |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    イベント ID     |                                       0x1FB0                                       |
|  イベント ソース   |                                         0                                          |
|    コンポーネント    |                                         0                                          |
|  シンボル名  |                          BTS_I_WCF_SERVICE_HOST_RESTARTED                          |
|  メッセージ テキスト   |                                         0                                          |
  
## <a name="explanation"></a>説明  
 このメッセージは、WCF アダプターが "参考" イベント ログ エントリを書き込む方法を示します (アダプター向けに用意された API では、情報ではなく警告またはエラーを作成できます)。  
  
## <a name="user-action"></a>ユーザーの操作  
 イベント ログにこの情報イベントが含まれている場合は、自動回復が正常に完了したことを示します。 このメッセージについてその他の操作は必要ありません。