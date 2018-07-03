---
title: 'インターチェンジで構造エラーが見つかりました。 最後の構造上有効な機能グループ ID が: |Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bd62855b-ecc6-4cfd-be9c-0025348eb841
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a3da8a701e543fe5bfb9453af3cfa2514414f5c2
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/27/2018
ms.locfileid: "36988099"
---
# <a name="the-interchange-had-structural-error-last-structurally-valid-functional-group-id-was"></a>インターチェンジで構造エラーが見つかりました。 構造上有効な最後の機能グループ ID: 
## <a name="details"></a>詳細  
  
|                 |                                                                                                                                                    |
|-----------------|----------------------------------------------------------------------------------------------------------------------------------------------------|
|  製品名   |                                 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                                 |
| 製品バージョン |                                             [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                                             |
|    イベント ID     |                                                                         -                                                                          |
|  イベント ソース   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI                               |
|    コンポーネント    |                                                                     EDI エンジン                                                                     |
|  シンボル名  |                                                     X12InterchangeStructuralErrorAfter1stGroup                                                     |
|  メッセージ テキスト   | Id を持つインターチェンジ '{0}'、送信者 id'{1}'、受信者 id '{2}' 構造エラーが発生します。 構造上有効な最後の機能グループ ID は '{3}' でした。 |
  
## <a name="explanation"></a>説明  
 このエラー/警告/情報イベントは、表示された機能グループの後にインターチェンジで構造エラーが発生したため、受信パイプラインで受信 X12 インターチェンジを処理できなかったことを示します。 このイベントは保存中のインターチェンジで発生し、トランザクション セットはエラー時に中断された可能性があります。 このエラーにより、このエラーを含むトランザクション セット (複数可) は中断されましたが、それ以外のトランザクション セットは保存されたバッチの一部として処理されました。  
  
## <a name="user-action"></a>ユーザーの操作  
 このエラーを解決するには、インターチェンジの送信者が構造上のエラーを修正した上で、インターチェンジを再送信してもらいます。