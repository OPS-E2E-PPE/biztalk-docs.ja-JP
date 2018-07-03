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
ms.openlocfilehash: ef9f7f4419d6c95b9b11343f395ab8e3d17c7c34
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "37021085"
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
 このエラーは、使用するサービスが一方向のサービスであり、誤って指定されたことを示します。  
  
## <a name="user-action"></a>ユーザーの操作  
 通信パターンを一方向から要求 - 応答に切り替える方法でサービスを修正します。 または、コードの誤りを削除します。
 
 