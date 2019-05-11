---
title: 通信方式エラー |Microsoft Docs
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
ms.openlocfilehash: 20a878f34b1e78509bec85fedbc2cf115a7140ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357040"
---
# <a name="communication-pattern-errors"></a>通信方式エラー
診断および WCF の通信方式エラーを解決するための情報です。  

## <a name="fault-messages-are-not-supported-on-one-way-ports"></a>エラー メッセージは一方向のポートではサポートされていません
  
|                 |                                                       エラーの詳細                                                       |
|-----------------|---------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                    [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                     |
| 製品バージョン |                                [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                 |
|    イベント ID     |                                                             0                                                             |
|  イベント ソース   |                                                             0                                                             |
|    コンポーネント    |                                                             0                                                             |
|  シンボル名  |                                                             0                                                             |
|  メッセージ テキスト   | エラー メッセージは一方向のポートではサポートされていません。 サービスの説明を修正"{0}「ポートの種類」{1}"し、ウィザードを再実行 |
  
## <a name="explanation"></a>説明  
 このエラーは、使用するサービスは、一方向サービスと指定したエラーを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 要求 - 応答の一方向通信パターンを切り替えることで、サービスを修正します。 または、コード障害を削除します。
 
 